---
title: 'Lync Server 2013: testar conexão do usuário para UM do Exchange'
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
ms.openlocfilehash: b72552f56041103e381291bf13ab13283a3c47ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="29ae5-102">Testando a conexão do usuário para o Exchange UM no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29ae5-102">Testing user connection to Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29ae5-103">_**Última modificação do tópico:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="29ae5-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29ae5-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="29ae5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="29ae5-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="29ae5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29ae5-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="29ae5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="29ae5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29ae5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29ae5-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="29ae5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="29ae5-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="29ae5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="29ae5-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsExUMConnectivity</strong> .</span><span class="sxs-lookup"><span data-stu-id="29ae5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="29ae5-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29ae5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="29ae5-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="29ae5-112">Description</span></span>

<span data-ttu-id="29ae5-113">O cmdlet **Test-CsExUMConnectivity** verifica se o usuário especificado pode se conectar ao serviço de Unificação de mensagens do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29ae5-113">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="29ae5-114">Observe que esse cmdlet verifica apenas se uma conexão pode ser feita com o serviço.</span><span class="sxs-lookup"><span data-stu-id="29ae5-114">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="29ae5-115">Ele não testará o serviço em si.</span><span class="sxs-lookup"><span data-stu-id="29ae5-115">It does not test the service itself.</span></span> <span data-ttu-id="29ae5-116">Para testar o serviço de mensagem unificada (executando um cmdlet de transação sintética que realmente deixa uma mensagem de caixa postal em uma caixa de correio do usuário), use o cmdlet Test-CsExUMVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="29ae5-116">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="29ae5-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="29ae5-117">Running the test</span></span>

<span data-ttu-id="29ae5-118">O exemplo a seguir testa a conectividade de Unificação de mensagens do Exchange para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="29ae5-118">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="29ae5-119">Este comando só funcionará se os usuários de teste foram definidos para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="29ae5-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="29ae5-120">Se eles tiverem, o comando determinará se o primeiro usuário de teste pode se conectar à unificação de mensagens.</span><span class="sxs-lookup"><span data-stu-id="29ae5-120">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="29ae5-121">Se os usuários de teste não foram configurados para o pool, o comando irá falhar.</span><span class="sxs-lookup"><span data-stu-id="29ae5-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="29ae5-122">Os comandos mostrados no exemplo a seguir testam a conectividade de Unificação\\de mensagens do Exchange para o usuário litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="29ae5-122">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="29ae5-123">Para fazer isso, o primeiro comando no exemplo usa o cmdlet **Get-Credential** para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell para\\o usuário litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="29ae5-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="29ae5-124">Observe que você deve fornecer a senha dessa conta para criar um objeto de credenciais válido e para garantir que o cmdlet **Test-CsExUMConnectivity** possa executar a verificação.</span><span class="sxs-lookup"><span data-stu-id="29ae5-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="29ae5-125">O segundo comando no exemplo usa o objeto de credenciais fornecido ($x) e o endereço SIP do usuário litwareinc\\kenmyer para determinar se ou este usuário pode se conectar à unificação de mensagens do Exchange.</span><span class="sxs-lookup"><span data-stu-id="29ae5-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="29ae5-126">O comando mostrado no exemplo a seguir é uma variação do comando que acabou de ser mostrado.</span><span class="sxs-lookup"><span data-stu-id="29ae5-126">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="29ae5-127">Nesse caso, o parâmetro OutLoggerVariable é incluído para gerar um log detalhado de cada etapa feita pelo **Test-CsExUMConnectivity** cmdletand o sucesso ou a falha de cada uma dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="29ae5-127">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="29ae5-128">Para fazer isso, o parâmetro OutLoggerVariable é adicionado junto com o valor de parâmetro ExumText; Isso faz com que informações de registro detalhadas sejam armazenadas em uma variável chamada $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="29ae5-128">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="29ae5-129">No comando final do exemplo, o método ToXML() é usado para converter a informação de log para um formato XML.</span><span class="sxs-lookup"><span data-stu-id="29ae5-129">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="29ae5-130">Em seguida, esses dados XML são gravados em um arquivo chamado C\\:\\logs ExumTest. xml usando o cmdlet Out-File.</span><span class="sxs-lookup"><span data-stu-id="29ae5-130">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="29ae5-131">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="29ae5-131">Determining success or failure</span></span>

<span data-ttu-id="29ae5-132">Se a integração do Exchange estiver configurada corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success**:</span><span class="sxs-lookup"><span data-stu-id="29ae5-132">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="29ae5-133">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29ae5-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="29ae5-134">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="29ae5-134">Result : Success</span></span>

<span data-ttu-id="29ae5-135">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="29ae5-135">Latency : 00:00:00</span></span>

<span data-ttu-id="29ae5-136">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="29ae5-136">Error Message :</span></span>

<span data-ttu-id="29ae5-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="29ae5-137">Diagnosis :</span></span>

<span data-ttu-id="29ae5-138">Se o usuário especificado não puder receber notificações, o resultado será mostrado como **falha**, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="29ae5-138">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="29ae5-139">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29ae5-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="29ae5-140">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="29ae5-140">Result : Failure</span></span>

<span data-ttu-id="29ae5-141">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="29ae5-141">Latency : 00:00:00</span></span>

<span data-ttu-id="29ae5-142">Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="29ae5-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="29ae5-143">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="29ae5-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="29ae5-144">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="29ae5-144">established connection failed because connected host has</span></span>

<span data-ttu-id="29ae5-145">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="29ae5-145">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="29ae5-146">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="29ae5-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="29ae5-147">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="29ae5-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="29ae5-148">a hora ou a conexão estabelecida falhou porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="29ae5-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="29ae5-149">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="29ae5-149">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="29ae5-150">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="29ae5-150">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="29ae5-151">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="29ae5-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="29ae5-152">Aqui estão alguns motivos comuns pelos quais **Test-CsExUMConnectivity** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="29ae5-152">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="29ae5-153">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="29ae5-153">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="29ae5-154">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="29ae5-154">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="29ae5-155">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="29ae5-155">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="29ae5-156">Esse comando falhará se o servidor Exchange estiver configurado incorretamente ou ainda não tiver sido implantado.</span><span class="sxs-lookup"><span data-stu-id="29ae5-156">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="29ae5-157">Esse comando falhará se o Exchange Server não estiver acessível pela rede.</span><span class="sxs-lookup"><span data-stu-id="29ae5-157">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29ae5-158">Confira também</span><span class="sxs-lookup"><span data-stu-id="29ae5-158">See Also</span></span>


[<span data-ttu-id="29ae5-159">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="29ae5-159">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

