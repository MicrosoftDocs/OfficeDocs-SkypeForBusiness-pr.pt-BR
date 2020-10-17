---
title: 'Lync Server 2013: testar acesso de repositório unificado de contatos'
description: 'Lync Server 2013: testar acesso de repositório unificado de contatos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58238685133c51130c414e0d7a8cd761d0233f5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556077"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="5f0c0-103">Testando o acesso de repositório unificado de contatos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f0c0-103">Testing Unified Contact Store access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f0c0-104">_**Última modificação do tópico:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="5f0c0-104">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f0c0-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="5f0c0-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5f0c0-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="5f0c0-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f0c0-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="5f0c0-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5f0c0-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f0c0-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f0c0-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="5f0c0-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5f0c0-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5f0c0-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsUnifiedContactStore</strong> .</span><span class="sxs-lookup"><span data-stu-id="5f0c0-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="5f0c0-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5f0c0-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5f0c0-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f0c0-113">Description</span></span>

<span data-ttu-id="5f0c0-114">O repositório unificado de contatos introduzido no Lync Server 2013 oferece aos administradores a opção de armazenar os contatos de um usuário no Microsoft Exchange Server 2013 em vez de no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-114">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="5f0c0-115">Isso permite que o usuário acesse o mesmo conjunto de contatos no Outlook Web Access, além do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-115">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="5f0c0-116">(Ou, você pode continuar a armazenar contatos no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-116">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="5f0c0-117">Nesse caso, os usuários terão que manter dois conjuntos separados de contatos: um para uso com o Outlook e o Outlook Web Access, e um para uso com o Lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="5f0c0-117">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="5f0c0-118">Você pode determinar se os contatos de um usuário foram movidos para o repositório unificado de contatos executando o cmdlet **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="5f0c0-118">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="5f0c0-119">O cmdlet **Test-CsUnifiedContactStore** usará a conta de usuário especificada, se conectará ao repositório unificado de contatos e tentará recuperar um contato para o usuário.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-119">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="5f0c0-120">Se não for possível recuperar nenhum contato, o comando falhará junto com a mensagem "nenhum contato foi recebido para o usuário.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-120">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="5f0c0-121">Verifique se os contatos existem para o usuário".</span><span class="sxs-lookup"><span data-stu-id="5f0c0-121">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="5f0c0-122">Observe que o cmdlet **Test-CsUnifiedContactStore** falhará se o usuário tiver migrado com êxito para o repositório unificado de contatos, mas não tiver contatos em sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-122">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="5f0c0-123">O usuário especificado deve ter pelo menos um contato para que o cmdlet **Test-CsUnifiedContactStore** seja concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-123">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5f0c0-124">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="5f0c0-124">Running the test</span></span>

<span data-ttu-id="5f0c0-125">Os comandos mostrados no exemplo a seguir determinam se os contatos do usuário litwareinc \\ kenmyer podem ser encontrados no repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-125">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="5f0c0-126">Para fazer isso, o primeiro comando no exemplo usa o cmdlet **Get-Credential** para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell para o usuário litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-126">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="5f0c0-127">Observe que você deve fornecer a senha dessa conta para criar um objeto de credenciais válido e para garantir que o cmdlet **Test-CsUnifiedContactStore** possa executar a verificação.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-127">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="5f0c0-128">O segundo comando no exemplo usa o objeto de credenciais fornecido ($x) e o endereço SIP do usuário litwareinc \\ kenmyer para determinar se seus contatos podem ser encontrados no repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-128">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5f0c0-129">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="5f0c0-129">Determining success or failure</span></span>

<span data-ttu-id="5f0c0-130">Se o acesso ao repositório de contatos estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**</span><span class="sxs-lookup"><span data-stu-id="5f0c0-130">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="5f0c0-131">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f0c0-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5f0c0-132">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="5f0c0-132">Result : Success</span></span>

<span data-ttu-id="5f0c0-133">Latência: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="5f0c0-133">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="5f0c0-134">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="5f0c0-134">Error Message :</span></span>

<span data-ttu-id="5f0c0-135">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5f0c0-135">Diagnosis :</span></span>

<span data-ttu-id="5f0c0-136">Se o acesso ao repositório de contatos não estiver configurado corretamente, o resultado será mostrado como **falha**, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="5f0c0-136">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5f0c0-137">Aviso: falha ao ler o número da porta do registrador para o fornecido totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="5f0c0-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="5f0c0-138">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="5f0c0-138">domain name (FQDN).</span></span> <span data-ttu-id="5f0c0-139">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-139">Using default Registrar port number.</span></span> <span data-ttu-id="5f0c0-140">Exceções</span><span class="sxs-lookup"><span data-stu-id="5f0c0-140">Exception:</span></span>

<span data-ttu-id="5f0c0-141">System. InvalidOperationException: nenhum cluster correspondente encontrado na topologia.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="5f0c0-142">por</span><span class="sxs-lookup"><span data-stu-id="5f0c0-142">at</span></span>

<span data-ttu-id="5f0c0-143">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="5f0c0-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="5f0c0-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="5f0c0-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="5f0c0-145">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f0c0-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5f0c0-146">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="5f0c0-146">Result : Failure</span></span>

<span data-ttu-id="5f0c0-147">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5f0c0-147">Latency : 00:00:00</span></span>

<span data-ttu-id="5f0c0-148">Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="5f0c0-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="5f0c0-149">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="5f0c0-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="5f0c0-150">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="5f0c0-150">established connection failed because connected host has</span></span>

<span data-ttu-id="5f0c0-151">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5f0c0-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5f0c0-152">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="5f0c0-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="5f0c0-153">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="5f0c0-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="5f0c0-154">a hora ou a conexão estabelecida falhou porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="5f0c0-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="5f0c0-155">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5f0c0-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5f0c0-156">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5f0c0-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5f0c0-157">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="5f0c0-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="5f0c0-158">Aqui estão alguns motivos comuns pelos quais **Test-CsUnifiedContactStore** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="5f0c0-158">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="5f0c0-159">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5f0c0-160">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5f0c0-161">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="5f0c0-162">Falha ao conectar ao repositório unificado de contatos e a tentativa de recuperar um contato para o usuário não foi possível.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-162">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="5f0c0-163">Pode haver problemas de conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="5f0c0-163">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f0c0-164">Confira também</span><span class="sxs-lookup"><span data-stu-id="5f0c0-164">See Also</span></span>


[<span data-ttu-id="5f0c0-165">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="5f0c0-165">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="5f0c0-166">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="5f0c0-166">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

