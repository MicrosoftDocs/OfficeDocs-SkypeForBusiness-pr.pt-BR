---
title: 'Lync Server 2013: testar conexão do usuário para UM do Exchange'
description: 'Lync Server 2013: testando conexão do usuário para UM do Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea6f7d446fe3fd98db67bab4ffee9cc976202689
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556058"
---
# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="9f92a-103">Testando a conexão do usuário para o Exchange UM no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f92a-103">Testing user connection to Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f92a-104">_**Última modificação do tópico:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="9f92a-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f92a-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="9f92a-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9f92a-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="9f92a-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f92a-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="9f92a-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9f92a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f92a-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f92a-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="9f92a-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9f92a-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9f92a-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9f92a-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsExUMConnectivity</strong> .</span><span class="sxs-lookup"><span data-stu-id="9f92a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="9f92a-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9f92a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9f92a-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f92a-113">Description</span></span>

<span data-ttu-id="9f92a-114">O cmdlet **Test-CsExUMConnectivity** verifica se o usuário especificado pode se conectar ao serviço de Unificação de mensagens do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f92a-114">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="9f92a-115">Observe que esse cmdlet verifica apenas se uma conexão pode ser feita com o serviço.</span><span class="sxs-lookup"><span data-stu-id="9f92a-115">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="9f92a-116">Ele não testará o serviço em si.</span><span class="sxs-lookup"><span data-stu-id="9f92a-116">It does not test the service itself.</span></span> <span data-ttu-id="9f92a-117">Para testar o serviço de mensagem unificada (executando um cmdlet de transação sintética que realmente deixa uma mensagem de caixa postal em uma caixa de correio do usuário), use o cmdlet Test-CsExUMVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="9f92a-117">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9f92a-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="9f92a-118">Running the test</span></span>

<span data-ttu-id="9f92a-119">O exemplo a seguir testa a conectividade de Unificação de mensagens do Exchange para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9f92a-119">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="9f92a-120">Este comando só funcionará se os usuários de teste foram definidos para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9f92a-120">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="9f92a-121">Se eles tiverem, o comando determinará se o primeiro usuário de teste pode se conectar à unificação de mensagens.</span><span class="sxs-lookup"><span data-stu-id="9f92a-121">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="9f92a-122">Se os usuários de teste não foram configurados para o pool, o comando irá falhar.</span><span class="sxs-lookup"><span data-stu-id="9f92a-122">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="9f92a-123">Os comandos mostrados no exemplo a seguir testam a conectividade de Unificação de mensagens do Exchange para o usuário litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="9f92a-123">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="9f92a-124">Para fazer isso, o primeiro comando no exemplo usa o cmdlet **Get-Credential** para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell para o usuário litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="9f92a-124">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="9f92a-125">Observe que você deve fornecer a senha dessa conta para criar um objeto de credenciais válido e para garantir que o cmdlet **Test-CsExUMConnectivity** possa executar a verificação.</span><span class="sxs-lookup"><span data-stu-id="9f92a-125">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="9f92a-126">O segundo comando no exemplo usa o objeto de credenciais fornecido ($x) e o endereço SIP do usuário litwareinc \\ kenmyer para determinar se ou este usuário pode se conectar à unificação de mensagens do Exchange.</span><span class="sxs-lookup"><span data-stu-id="9f92a-126">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="9f92a-127">O comando mostrado no exemplo a seguir é uma variação do comando que acabou de ser mostrado.</span><span class="sxs-lookup"><span data-stu-id="9f92a-127">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="9f92a-128">Nesse caso, o parâmetro OutLoggerVariable é incluído para gerar um log detalhado de cada etapa feita pelo **Test-CsExUMConnectivity** cmdletand o sucesso ou a falha de cada uma dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="9f92a-128">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="9f92a-129">Para fazer isso, o parâmetro OutLoggerVariable é adicionado junto com o valor de parâmetro ExumText; Isso faz com que informações de registro detalhadas sejam armazenadas em uma variável chamada $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="9f92a-129">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="9f92a-130">No comando final do exemplo, o método ToXML() é usado para converter a informação de log para um formato XML.</span><span class="sxs-lookup"><span data-stu-id="9f92a-130">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="9f92a-131">Em seguida, esses dados XML são gravados em um arquivo chamado C: \\ Logs \\ExumTest.xml usando o cmdlet Out-File.</span><span class="sxs-lookup"><span data-stu-id="9f92a-131">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9f92a-132">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="9f92a-132">Determining success or failure</span></span>

<span data-ttu-id="9f92a-133">Se a integração do Exchange estiver configurada corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success**:</span><span class="sxs-lookup"><span data-stu-id="9f92a-133">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="9f92a-134">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f92a-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f92a-135">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="9f92a-135">Result : Success</span></span>

<span data-ttu-id="9f92a-136">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9f92a-136">Latency : 00:00:00</span></span>

<span data-ttu-id="9f92a-137">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="9f92a-137">Error Message :</span></span>

<span data-ttu-id="9f92a-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9f92a-138">Diagnosis :</span></span>

<span data-ttu-id="9f92a-139">Se o usuário especificado não puder receber notificações, o resultado será mostrado como **falha**, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="9f92a-139">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9f92a-140">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f92a-140">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f92a-141">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="9f92a-141">Result : Failure</span></span>

<span data-ttu-id="9f92a-142">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9f92a-142">Latency : 00:00:00</span></span>

<span data-ttu-id="9f92a-143">Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="9f92a-143">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="9f92a-144">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="9f92a-144">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="9f92a-145">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="9f92a-145">established connection failed because connected host has</span></span>

<span data-ttu-id="9f92a-146">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="9f92a-146">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="9f92a-147">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="9f92a-147">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="9f92a-148">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="9f92a-148">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="9f92a-149">a hora ou a conexão estabelecida falhou porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="9f92a-149">time, or established connection failed because connected host</span></span>

<span data-ttu-id="9f92a-150">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="9f92a-150">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="9f92a-151">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9f92a-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9f92a-152">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="9f92a-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="9f92a-153">Aqui estão alguns motivos comuns pelos quais **Test-CsExUMConnectivity** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="9f92a-153">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="9f92a-154">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="9f92a-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="9f92a-155">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="9f92a-155">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="9f92a-156">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="9f92a-156">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="9f92a-157">Esse comando falhará se o servidor Exchange estiver configurado incorretamente ou ainda não tiver sido implantado.</span><span class="sxs-lookup"><span data-stu-id="9f92a-157">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="9f92a-158">Esse comando falhará se o Exchange Server não estiver acessível pela rede.</span><span class="sxs-lookup"><span data-stu-id="9f92a-158">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f92a-159">Confira também</span><span class="sxs-lookup"><span data-stu-id="9f92a-159">See Also</span></span>


[<span data-ttu-id="9f92a-160">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="9f92a-160">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

