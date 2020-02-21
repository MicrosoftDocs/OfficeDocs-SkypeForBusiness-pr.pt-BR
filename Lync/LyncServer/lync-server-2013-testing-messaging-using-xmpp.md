---
title: 'Lync Server 2013: testar mensagens usando XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61eb53c5c2f3cfe74087599535541cfb8286ab55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="b1129-102">Testando mensagens usando o XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1129-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1129-103">_**Última modificação do tópico:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="b1129-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1129-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="b1129-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b1129-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="b1129-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1129-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="b1129-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b1129-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1129-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1129-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="b1129-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b1129-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b1129-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b1129-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsXmppIM</strong> .</span><span class="sxs-lookup"><span data-stu-id="b1129-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="b1129-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b1129-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b1129-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b1129-112">Description</span></span>

<span data-ttu-id="b1129-113">O XMPP é um protocolo de comunicações padrão (baseado em XML) usado para enviar mensagens pela Internet.</span><span class="sxs-lookup"><span data-stu-id="b1129-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="b1129-114">O XMPP foi originalmente nomeado Jabber e é suportado por vários aplicativos de comunicação e mensagens da Internet, como o Google Talk e o chat do Facebook.</span><span class="sxs-lookup"><span data-stu-id="b1129-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="b1129-115">O cmdlet **Test-CsXmppIM** verifica se um usuário pode trocar mensagens instantâneas com um usuário em uma rede do XMPP.</span><span class="sxs-lookup"><span data-stu-id="b1129-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="b1129-116">Observe que, para esse teste ser bem-sucedido, você deve ter um endereço SIP válido para o usuário do XMPP e esse endereço SIP deve estar em uma rede configurada como um parceiro do XMPP permitido.</span><span class="sxs-lookup"><span data-stu-id="b1129-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b1129-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="b1129-117">Running the test</span></span>

<span data-ttu-id="b1129-118">O exemplo a seguir verifica as funcionalidades de mensagens instantâneas do XMPP para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b1129-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b1129-119">Este comando só funcionará se os usuários de teste estiverem definidos para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b1129-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b1129-120">Se eles tiverem, o comando determinará se o primeiro usuário de teste pode enviar uma mensagem instantânea XMPP para um usuário que tenha o endereço SIP adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b1129-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="b1129-121">Se os usuários de teste não estiverem definidos, o comando falhará porque não saberá qual usuário fará logon como.</span><span class="sxs-lookup"><span data-stu-id="b1129-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="b1129-122">Se você não definiu os usuários de teste para um pool, deverá incluir o parâmetro UserSipAddress e as credenciais do usuário que o comando deve usar ao tentar fazer logon.</span><span class="sxs-lookup"><span data-stu-id="b1129-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="b1129-123">Os comandos mostrados no exemplo a seguir testam a capacidade de um usuário específico\\(litwareinc pilar) fazer logon para enviar uma mensagem instantânea XMPP para o usuário adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b1129-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="b1129-124">Para fazer isso, o primeiro comando no exemplo usa o cmdlet Get-Credential para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contenha o nome e a senha do usuário pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="b1129-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="b1129-125">(Como o nome de logon\\litwareinc pilar foi incluído como um parâmetro, a caixa de diálogo de solicitação de credenciais do Windows PowerShell só exige que o administrador insira a senha da conta pilar Ackerman.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="b1129-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="b1129-126">Em seguida, o segundo comando verifica se esse usuário pode fazer logon no pool atl-cs-001.litwareinc.com e enviar a mensagem instantânea XMPP.</span><span class="sxs-lookup"><span data-stu-id="b1129-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="b1129-127">Para executar essa tarefa, o cmdlet **Test-CsXmppIm** é chamado, juntamente com quatro parâmetros: TargetFqdn (o FQDN do pool de registrador); Destinatário (o endereço SIP do usuário para o qual a mensagem está sendo endereçada); Usercredential (o objeto Windows PowerShell que contém as credenciais de usuário de pilar Ackerman); e UserSipAddress (o endereço SIP que corresponde às credenciais de usuário fornecidas).</span><span class="sxs-lookup"><span data-stu-id="b1129-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b1129-128">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="b1129-128">Determining success or failure</span></span>

<span data-ttu-id="b1129-129">Se o sistema de mensagens instantâneas do XMPP estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="b1129-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b1129-130">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b1129-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b1129-131">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="b1129-131">Result : Success</span></span>

<span data-ttu-id="b1129-132">Latência: 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="b1129-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="b1129-133">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="b1129-133">Error Message :</span></span>

<span data-ttu-id="b1129-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b1129-134">Diagnosis :</span></span>

<span data-ttu-id="b1129-135">Se os usuários especificados não puderem usar o sistema de mensagens instantâneas do XMPP, o resultado será mostrado como **falha**, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="b1129-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b1129-136">Aviso: falha ao ler o número da porta do registrador para o fornecido totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="b1129-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="b1129-137">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="b1129-137">domain name (FQDN).</span></span> <span data-ttu-id="b1129-138">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="b1129-138">Using default Registrar port number.</span></span> <span data-ttu-id="b1129-139">Exceções</span><span class="sxs-lookup"><span data-stu-id="b1129-139">Exception:</span></span>

<span data-ttu-id="b1129-140">System. InvalidOperationException: nenhum cluster correspondente encontrado na topologia.</span><span class="sxs-lookup"><span data-stu-id="b1129-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="b1129-141">por</span><span class="sxs-lookup"><span data-stu-id="b1129-141">at</span></span>

<span data-ttu-id="b1129-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="b1129-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="b1129-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="b1129-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="b1129-144">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b1129-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b1129-145">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="b1129-145">Result : Failure</span></span>

<span data-ttu-id="b1129-146">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b1129-146">Latency : 00:00:00</span></span>

<span data-ttu-id="b1129-147">Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="b1129-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="b1129-148">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="b1129-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="b1129-149">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="b1129-149">established connection failed because connected host has</span></span>

<span data-ttu-id="b1129-150">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b1129-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b1129-151">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="b1129-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="b1129-152">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="b1129-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="b1129-153">a hora ou a conexão estabelecida falhou porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="b1129-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="b1129-154">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b1129-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b1129-155">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b1129-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b1129-156">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="b1129-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="b1129-157">Aqui estão alguns motivos comuns pelos quais **Test-CsXmppIM** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="b1129-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="b1129-158">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="b1129-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b1129-159">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="b1129-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b1129-160">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="b1129-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b1129-161">Esse comando falhará se a configuração de gateway do XMPP estiver configurada incorretamente ou ainda não tiver sido implantada.</span><span class="sxs-lookup"><span data-stu-id="b1129-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1129-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="b1129-162">See Also</span></span>


[<span data-ttu-id="b1129-163">Set-CsXmppGatewayConfiguration</span><span class="sxs-lookup"><span data-stu-id="b1129-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

