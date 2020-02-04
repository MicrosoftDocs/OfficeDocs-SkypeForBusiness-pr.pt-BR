---
title: 'Lync Server 2013: testar a conexão do usuário com o correio de voz do Exchange UM'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c533781fedc3bf3d6266bae80e5c59cacbec4874
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="a34f1-102">Testando a conexão do usuário com o correio de voz do Exchange no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a34f1-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a34f1-103">_**Tópico da última modificação:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="a34f1-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a34f1-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="a34f1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a34f1-105">Diário</span><span class="sxs-lookup"><span data-stu-id="a34f1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a34f1-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="a34f1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a34f1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a34f1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a34f1-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="a34f1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a34f1-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a34f1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a34f1-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsExUMVoiceMail</strong> .</span><span class="sxs-lookup"><span data-stu-id="a34f1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="a34f1-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a34f1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a34f1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="a34f1-112">Description</span></span>

<span data-ttu-id="a34f1-113">O cmdlet **Test-CsExUMVoiceMail** permite que os administradores verifiquem se um usuário pode acessar e usar o serviço de mensagens unificadas do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a34f1-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="a34f1-114">Para fazer isso, o cmdlet se conecta ao serviço de Unificação de mensagens e deixa uma caixa postal na caixa de correio especificada.</span><span class="sxs-lookup"><span data-stu-id="a34f1-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="a34f1-115">Pode ser uma caixa postal fornecida pelo sistema ou pode ser um personalizada. WAV que você mesmo gravou.</span><span class="sxs-lookup"><span data-stu-id="a34f1-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a34f1-116">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="a34f1-116">Running the test</span></span>

<span data-ttu-id="a34f1-117">O exemplo a seguir testa a conectividade da caixa postal do Exchange Unified Messaging para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a34f1-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="a34f1-118">Esse comando funcionará apenas se os usuários de teste tiverem sido definidos para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a34f1-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="a34f1-119">Se eles tiverem, o comando determinará se o primeiro usuário de teste pode usar a caixa postal de mensagens unificadas.</span><span class="sxs-lookup"><span data-stu-id="a34f1-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="a34f1-120">Se os usuários de teste não tiverem sido configurados para o pool, o comando irá falhar.</span><span class="sxs-lookup"><span data-stu-id="a34f1-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="a34f1-121">Os comandos mostrados no próximo exemplo testam a conectividade da caixa postal do Exchange Unified\\Messaging para o usuário litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="a34f1-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="a34f1-122">Para fazer isso, o primeiro comando do exemplo usa o cmdlet **Get-Credential** para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell para\\o usuário litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="a34f1-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="a34f1-123">Observe que você deve fornecer a senha desta conta para criar um objeto de credenciais válido e para garantir que o cmdlet **Test-CsExUMVoiceMail** possa executar sua verificação.</span><span class="sxs-lookup"><span data-stu-id="a34f1-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="a34f1-124">O segundo comando do exemplo usa o objeto de credenciais fornecido ($x) e o endereço SIP do usuário litwareinc\\kenmyer para determinar se ou este usuário pode se conectar à caixa postal do Exchange Unified Messaging.</span><span class="sxs-lookup"><span data-stu-id="a34f1-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="a34f1-125">O comando mostrado no próximo exemplo é uma variação do comando mostrado no exemplo 1; Nesse caso, o parâmetro OutLoggerVariable é incluído para gerar um log detalhado de cada etapa feita pelo **Test-CsExUMVoiceMail** cmdletand o êxito ou falha de cada uma dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="a34f1-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="a34f1-126">Para fazer isso, o parâmetro OutLoggerVariable é adicionado juntamente com o valor de parâmetro ExumText; Isso faz com que as informações de registro detalhadas sejam armazenadas em uma variável chamada $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="a34f1-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="a34f1-127">No comando final do exemplo, o método ToXML () é usado para converter as informações de log em formato XML.</span><span class="sxs-lookup"><span data-stu-id="a34f1-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="a34f1-128">Em seguida, esses dados XML são gravados em um arquivo chamado C\\:\\registra o VoicemailTest. xml usando o cmdlet Out-File.</span><span class="sxs-lookup"><span data-stu-id="a34f1-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a34f1-129">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="a34f1-129">Determining success or failure</span></span>

<span data-ttu-id="a34f1-130">Se a integração com o Exchange estiver configurada corretamente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success**:</span><span class="sxs-lookup"><span data-stu-id="a34f1-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="a34f1-131">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a34f1-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a34f1-132">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="a34f1-132">Result : Success</span></span>

<span data-ttu-id="a34f1-133">Latência: 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="a34f1-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="a34f1-134">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="a34f1-134">Error Message :</span></span>

<span data-ttu-id="a34f1-135">Correto</span><span class="sxs-lookup"><span data-stu-id="a34f1-135">Diagnosis :</span></span>

<span data-ttu-id="a34f1-136">Se o usuário especificado não conseguir se conectar ao correio de voz, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="a34f1-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a34f1-137">Aviso: falha ao ler o número da porta do registrador para o número da porta de dados totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="a34f1-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="a34f1-138">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="a34f1-138">domain name (FQDN).</span></span> <span data-ttu-id="a34f1-139">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="a34f1-139">Using default Registrar port number.</span></span> <span data-ttu-id="a34f1-140">Extremamente</span><span class="sxs-lookup"><span data-stu-id="a34f1-140">Exception:</span></span>

<span data-ttu-id="a34f1-141">System. InvalidOperationException: nenhum cluster correspondente localizado na topologia.</span><span class="sxs-lookup"><span data-stu-id="a34f1-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="a34f1-142">como</span><span class="sxs-lookup"><span data-stu-id="a34f1-142">at</span></span>

<span data-ttu-id="a34f1-143">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="a34f1-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="a34f1-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="a34f1-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="a34f1-145">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a34f1-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a34f1-146">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="a34f1-146">Result : Failure</span></span>

<span data-ttu-id="a34f1-147">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a34f1-147">Latency : 00:00:00</span></span>

<span data-ttu-id="a34f1-148">Mensagem de erro: 10060, falha na tentativa de conexão porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="a34f1-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="a34f1-149">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="a34f1-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="a34f1-150">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="a34f1-150">established connection failed because connected host has</span></span>

<span data-ttu-id="a34f1-151">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="a34f1-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="a34f1-152">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="a34f1-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="a34f1-153">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="a34f1-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="a34f1-154">falha na hora ou estabelecida a conexão porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="a34f1-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="a34f1-155">falhou ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="a34f1-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="a34f1-156">Correto</span><span class="sxs-lookup"><span data-stu-id="a34f1-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a34f1-157">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="a34f1-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="a34f1-158">Aqui estão alguns motivos comuns pelos quais **Test-CsExUMVoiceMail** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="a34f1-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="a34f1-159">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="a34f1-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="a34f1-160">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="a34f1-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="a34f1-161">Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="a34f1-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="a34f1-162">Esse comando falhará se o Exchange Server estiver configurado incorretamente ou ainda não foi implantado.</span><span class="sxs-lookup"><span data-stu-id="a34f1-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a34f1-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="a34f1-163">See Also</span></span>


[<span data-ttu-id="a34f1-164">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="a34f1-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

