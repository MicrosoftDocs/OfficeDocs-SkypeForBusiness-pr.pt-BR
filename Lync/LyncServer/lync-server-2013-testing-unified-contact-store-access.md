---
title: 'Lync Server 2013: testando o acesso ao repositório de contatos unificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef1d8d8930b9e732faeef02c76d722331c726b67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="c4945-102">Testando o acesso a repositório de contatos unificado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4945-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4945-103">_**Tópico da última modificação:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="c4945-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4945-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="c4945-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c4945-105">Diário</span><span class="sxs-lookup"><span data-stu-id="c4945-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4945-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="c4945-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c4945-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4945-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4945-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="c4945-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c4945-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c4945-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c4945-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsUnifiedContactStore</strong> .</span><span class="sxs-lookup"><span data-stu-id="c4945-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="c4945-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c4945-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c4945-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c4945-112">Description</span></span>

<span data-ttu-id="c4945-113">O repositório de contatos Unificado apresentado no Lync Server 2013 fornece aos administradores a opção de armazenar os contatos de um usuário no Microsoft Exchange Server 2013 em vez de no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4945-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="c4945-114">Isso permite que o usuário acesse o mesmo conjunto de contatos no Outlook Web Access, além do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c4945-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="c4945-115">(Ou você pode continuar a armazenar contatos no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4945-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="c4945-116">Nesse caso, os usuários precisarão manter dois conjuntos de contatos separados: um para uso com o Outlook e o Outlook Web Access e um para uso com o Lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="c4945-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="c4945-117">Você pode determinar se os contatos de um usuário foram movidos para o repositório de contatos unificado executando o cmdlet **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="c4945-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="c4945-118">O cmdlet **Test-CsUnifiedContactStore** usará a conta de usuário especificada, se conectará ao repositório de contatos unificado e tentará recuperar um contato para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c4945-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="c4945-119">Se não for possível recuperar nenhum contato, o comando falhará junto com a mensagem "nenhum contato foi recebido para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c4945-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="c4945-120">Verifique se os contatos existem para o usuário. "</span><span class="sxs-lookup"><span data-stu-id="c4945-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="c4945-121">Observe que o cmdlet **Test-CsUnifiedContactStore** falhará se o usuário tiver migrado com êxito para o repositório de contatos unificado, mas não tiver contatos na lista de contatos dela.</span><span class="sxs-lookup"><span data-stu-id="c4945-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="c4945-122">O usuário especificado deve ter pelo menos um contato para que o cmdlet **Test-CsUnifiedContactStore** seja concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="c4945-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c4945-123">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="c4945-123">Running the test</span></span>

<span data-ttu-id="c4945-124">Os comandos mostrados no exemplo a seguir determinam se os contatos do\\usuário litwareinc kenmyer podem ser encontrados no repositório de contatos unificado.</span><span class="sxs-lookup"><span data-stu-id="c4945-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="c4945-125">Para fazer isso, o primeiro comando do exemplo usa o cmdlet **Get-Credential** para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell para\\o usuário litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="c4945-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="c4945-126">Observe que você deve fornecer a senha desta conta para criar um objeto de credenciais válido e verificar se o cmdlet **Test-CsUnifiedContactStore** pode executar sua verificação.</span><span class="sxs-lookup"><span data-stu-id="c4945-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="c4945-127">O segundo comando do exemplo usa o objeto de credenciais fornecido ($x) e o endereço SIP do usuário litwareinc\\kenmyer para determinar se seus contatos podem ser encontrados no repositório de contatos unificado.</span><span class="sxs-lookup"><span data-stu-id="c4945-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c4945-128">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="c4945-128">Determining success or failure</span></span>

<span data-ttu-id="c4945-129">Se o acesso ao repositório de contatos estiver configurado corretamente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="c4945-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="c4945-130">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c4945-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c4945-131">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="c4945-131">Result : Success</span></span>

<span data-ttu-id="c4945-132">Latência: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="c4945-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="c4945-133">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="c4945-133">Error Message :</span></span>

<span data-ttu-id="c4945-134">Correto</span><span class="sxs-lookup"><span data-stu-id="c4945-134">Diagnosis :</span></span>

<span data-ttu-id="c4945-135">Se o acesso ao repositório de contatos não estiver configurado corretamente, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="c4945-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c4945-136">Aviso: falha ao ler o número da porta do registrador para o número da porta de dados totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="c4945-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="c4945-137">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="c4945-137">domain name (FQDN).</span></span> <span data-ttu-id="c4945-138">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="c4945-138">Using default Registrar port number.</span></span> <span data-ttu-id="c4945-139">Extremamente</span><span class="sxs-lookup"><span data-stu-id="c4945-139">Exception:</span></span>

<span data-ttu-id="c4945-140">System. InvalidOperationException: nenhum cluster correspondente localizado na topologia.</span><span class="sxs-lookup"><span data-stu-id="c4945-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="c4945-141">como</span><span class="sxs-lookup"><span data-stu-id="c4945-141">at</span></span>

<span data-ttu-id="c4945-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="c4945-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="c4945-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="c4945-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="c4945-144">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c4945-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c4945-145">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="c4945-145">Result : Failure</span></span>

<span data-ttu-id="c4945-146">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c4945-146">Latency : 00:00:00</span></span>

<span data-ttu-id="c4945-147">Mensagem de erro: 10060, falha na tentativa de conexão porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="c4945-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="c4945-148">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="c4945-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="c4945-149">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="c4945-149">established connection failed because connected host has</span></span>

<span data-ttu-id="c4945-150">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="c4945-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c4945-151">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="c4945-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="c4945-152">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="c4945-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="c4945-153">falha na hora ou estabelecida a conexão porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="c4945-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="c4945-154">falhou ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="c4945-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c4945-155">Correto</span><span class="sxs-lookup"><span data-stu-id="c4945-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c4945-156">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="c4945-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="c4945-157">Aqui estão alguns motivos comuns pelos quais **Test-CsUnifiedContactStore** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="c4945-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="c4945-158">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="c4945-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="c4945-159">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="c4945-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="c4945-160">Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="c4945-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="c4945-161">Não foi possível conectar-se ao repositório de contatos unificado, e a tentativa de recuperar um contato para o usuário não foi possível.</span><span class="sxs-lookup"><span data-stu-id="c4945-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="c4945-162">Pode haver problemas de conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="c4945-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c4945-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="c4945-163">See Also</span></span>


[<span data-ttu-id="c4945-164">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="c4945-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="c4945-165">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="c4945-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

