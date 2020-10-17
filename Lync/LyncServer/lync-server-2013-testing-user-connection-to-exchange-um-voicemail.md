---
title: 'Lync Server 2013: testar conexão do usuário para caixa postal do UM do Exchange'
description: 'Lync Server 2013: testar a conexão do usuário com a caixa postal do UM do Exchange.'
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
ms.openlocfilehash: b887b5b0df02a5864e0a39f2b62893d20105a86a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552607"
---
# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="1f795-103">Testar a conexão do usuário com a caixa postal do UM do Exchange no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f795-103">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f795-104">_**Última modificação do tópico:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="1f795-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f795-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="1f795-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1f795-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="1f795-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f795-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="1f795-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1f795-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f795-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f795-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="1f795-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1f795-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1f795-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1f795-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsExUMVoiceMail</strong> .</span><span class="sxs-lookup"><span data-stu-id="1f795-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="1f795-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1f795-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1f795-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f795-113">Description</span></span>

<span data-ttu-id="1f795-114">O cmdlet **Test-CsExUMVoiceMail** permite que os administradores verifiquem se um usuário pode acessar e usar o serviço de Unificação de mensagens do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f795-114">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="1f795-115">Para fazer isso, o cmdlet conecta-se ao serviço de mensagem unificada e deixa uma mensagem de voz na caixa de correio especificada.</span><span class="sxs-lookup"><span data-stu-id="1f795-115">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="1f795-116">Isso pode ser uma caixa postal fornecida pelo sistema ou ser um arquivo .WAV personalizado que você gravou sozinho.</span><span class="sxs-lookup"><span data-stu-id="1f795-116">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1f795-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="1f795-117">Running the test</span></span>

<span data-ttu-id="1f795-118">O exemplo a seguir testa a conectividade de caixa postal do Exchange Unified Messaging para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="1f795-118">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="1f795-119">Este comando só funcionará se os usuários de teste foram definidos para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="1f795-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="1f795-120">Se houver, o comando determinará se o primeiro usuário de teste pode usar a caixa postal de Unificação de mensagens.</span><span class="sxs-lookup"><span data-stu-id="1f795-120">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="1f795-121">Se os usuários de teste não foram configurados para o pool, o comando irá falhar.</span><span class="sxs-lookup"><span data-stu-id="1f795-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="1f795-122">Os comandos mostrados no exemplo a seguir testam a conectividade de caixa postal de Unificação de mensagens do Exchange para o usuário litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="1f795-122">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="1f795-123">Para fazer isso, o primeiro comando no exemplo usa o cmdlet **Get-Credential** para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell para o usuário litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="1f795-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="1f795-124">Observe que você deve fornecer a senha dessa conta para criar um objeto de credenciais válido e para garantir que o cmdlet **Test-CsExUMVoiceMail** possa executar a verificação.</span><span class="sxs-lookup"><span data-stu-id="1f795-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="1f795-125">O segundo comando no exemplo usa o objeto de credenciais fornecido ($x) e o endereço SIP do usuário litwareinc \\ kenmyer para determinar se ou este usuário pode se conectar a uma caixa postal do Exchange Unified Messaging.</span><span class="sxs-lookup"><span data-stu-id="1f795-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="1f795-126">O comando mostrado no exemplo a seguir é uma variação do comando mostrado no exemplo 1; Nesse caso, o parâmetro OutLoggerVariable é incluído para gerar um log detalhado de cada etapa feita pelo **Test-CsExUMVoiceMail** cmdletand o sucesso ou a falha de cada uma dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="1f795-126">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="1f795-127">Para fazer isso, o parâmetro OutLoggerVariable é adicionado junto com o valor do parâmetro ExumText; Isso faz com que informações de registro detalhadas sejam armazenadas em uma variável chamada $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="1f795-127">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="1f795-128">No comando final do exemplo, o método ToXML() é usado para converter a informação de log para um formato XML.</span><span class="sxs-lookup"><span data-stu-id="1f795-128">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="1f795-129">Em seguida, esses dados XML são gravados em um arquivo chamado C: \\ Logs \\VoicemailTest.xml usando o cmdlet Out-File.</span><span class="sxs-lookup"><span data-stu-id="1f795-129">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1f795-130">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="1f795-130">Determining success or failure</span></span>

<span data-ttu-id="1f795-131">Se a integração do Exchange estiver configurada corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success**:</span><span class="sxs-lookup"><span data-stu-id="1f795-131">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="1f795-132">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1f795-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1f795-133">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="1f795-133">Result : Success</span></span>

<span data-ttu-id="1f795-134">Latência: 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="1f795-134">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="1f795-135">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="1f795-135">Error Message :</span></span>

<span data-ttu-id="1f795-136">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1f795-136">Diagnosis :</span></span>

<span data-ttu-id="1f795-137">Se o usuário especificado não puder se conectar ao correio de voz, o resultado será mostrado como **falha**e as informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="1f795-137">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1f795-138">Aviso: falha ao ler o número da porta do registrador para o fornecido totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="1f795-138">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="1f795-139">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="1f795-139">domain name (FQDN).</span></span> <span data-ttu-id="1f795-140">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="1f795-140">Using default Registrar port number.</span></span> <span data-ttu-id="1f795-141">Exceções</span><span class="sxs-lookup"><span data-stu-id="1f795-141">Exception:</span></span>

<span data-ttu-id="1f795-142">System. InvalidOperationException: nenhum cluster correspondente encontrado na topologia.</span><span class="sxs-lookup"><span data-stu-id="1f795-142">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="1f795-143">por</span><span class="sxs-lookup"><span data-stu-id="1f795-143">at</span></span>

<span data-ttu-id="1f795-144">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="1f795-144">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="1f795-145">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="1f795-145">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="1f795-146">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1f795-146">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1f795-147">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="1f795-147">Result : Failure</span></span>

<span data-ttu-id="1f795-148">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="1f795-148">Latency : 00:00:00</span></span>

<span data-ttu-id="1f795-149">Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="1f795-149">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="1f795-150">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="1f795-150">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="1f795-151">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="1f795-151">established connection failed because connected host has</span></span>

<span data-ttu-id="1f795-152">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="1f795-152">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="1f795-153">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="1f795-153">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="1f795-154">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="1f795-154">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="1f795-155">a hora ou a conexão estabelecida falhou porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="1f795-155">time, or established connection failed because connected host</span></span>

<span data-ttu-id="1f795-156">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="1f795-156">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="1f795-157">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1f795-157">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1f795-158">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="1f795-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="1f795-159">Aqui estão alguns motivos comuns pelos quais **Test-CsExUMVoiceMail** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="1f795-159">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="1f795-160">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="1f795-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="1f795-161">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="1f795-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="1f795-162">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="1f795-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="1f795-163">Esse comando falhará se o servidor Exchange estiver configurado incorretamente ou ainda não tiver sido implantado.</span><span class="sxs-lookup"><span data-stu-id="1f795-163">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f795-164">Confira também</span><span class="sxs-lookup"><span data-stu-id="1f795-164">See Also</span></span>


[<span data-ttu-id="1f795-165">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="1f795-165">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

