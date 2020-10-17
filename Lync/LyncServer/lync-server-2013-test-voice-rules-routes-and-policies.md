---
title: 'Lync Server 2013: testar regras de voz, rotas e políticas'
description: 'Lync Server 2013: testar regras de voz, rotas e políticas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf205ac2585298dfc5347d93e382e8bbda9f3ff4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557037"
---
# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="fa8fd-103">Testar regras de voz, rotas e políticas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa8fd-103">Test voice rules, routes, and policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa8fd-104">_**Última modificação do tópico:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="fa8fd-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa8fd-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="fa8fd-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fa8fd-106">Mensal</span><span class="sxs-lookup"><span data-stu-id="fa8fd-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa8fd-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="fa8fd-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fa8fd-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa8fd-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa8fd-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="fa8fd-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fa8fd-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fa8fd-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="fa8fd-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fa8fd-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="fa8fd-113">Description</span></span>

<span data-ttu-id="fa8fd-114">Quando um usuário faz uma chamada telefônica, a rota que a chamada leva para chegar ao seu destino depende das políticas e dos planos de discagem atribuídos a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-114">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="fa8fd-115">Dado o endereço SIP de um usuário e um número de telefone, o cmdlet Test-CsVoiceUser verifica se o usuário em questão pode concluir uma chamada para esse número.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-115">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="fa8fd-116">Se o teste for bem-sucedido, Test-CsVoiceUser retornará o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-116">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="fa8fd-117">O número convertido no formato E. 164 (com base no plano de discagem do usuário)</span><span class="sxs-lookup"><span data-stu-id="fa8fd-117">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="fa8fd-118">A regra de normalização que forneceu essa tradução</span><span class="sxs-lookup"><span data-stu-id="fa8fd-118">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="fa8fd-119">A rota de voz usada (com base na prioridade da rota);</span><span class="sxs-lookup"><span data-stu-id="fa8fd-119">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="fa8fd-120">O uso de telefone que vinculou a política de voz do usuário à rota de voz.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-120">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="fa8fd-121">Test-CsVoiceUser permite que você determine se um número de telefone específico irá encaminhar e traduzir conforme o esperado e pode ajudar a solucionar problemas relacionados a chamadas que são experientes por usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-121">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fa8fd-122">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="fa8fd-122">Running the test</span></span>

<span data-ttu-id="fa8fd-123">Ao executar o cmdlet Test-CsVoiceUser você deve fornecer duas partes de informação: o número que está sendo discado (DialedNumber) e a identidade da conta de usuário que está sendo testada.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-123">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="fa8fd-124">Por exemplo, este comando testa a capacidade do usuário que tem o endereço SIP sip:kenmyer@litwareinc.com para fazer uma chamada para o número de telefone + 1206555-1219:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-124">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="fa8fd-125">O número de telefone deve ser formatado da forma que você espera que ele seja discado.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-125">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="fa8fd-126">Por exemplo, se os usuários normalmente não discam o 1 antes de colocar uma chamada de longa distância, você deve usar este formato:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-126">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="fa8fd-127">Obviamente, nesse caso, o teste falhará se você não tiver uma regra de normalização que possa converter corretamente o número 2065551219 no formato de telefone E. 164 que é usado pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-127">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="fa8fd-128">Para obter mais informações, consulte o tópico de ajuda New-CsVoiceNormalizationRule cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-128">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="fa8fd-129">Se quiser executar esse mesmo teste em relação a cada uma das suas contas de usuário, você poderá usar um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-129">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="fa8fd-130">Para obter mais informações, consulte a documentação de ajuda para o cmdlet Test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-130">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fa8fd-131">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="fa8fd-131">Determining success or failure</span></span>

<span data-ttu-id="fa8fd-132">Se o teste for concluído com êxito (ou seja, se o usuário puder fazer uma chamada telefônica para o número especificado), a saída mostrará informações como o número de telefone convertido e a regra de normalização e a rota de voz correspondente:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-132">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="fa8fd-133">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="fa8fd-133">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="fa8fd-134">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="fa8fd-134">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="fa8fd-135">\+12065551219 Descripti...    Local LocalRoute</span><span class="sxs-lookup"><span data-stu-id="fa8fd-135">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="fa8fd-136">Devido às limitações da tela do Windows PowerShell, pelo menos algumas informações retornadas (mais notavelmente a descrição completa da regra de normalização correspondente) podem não aparecer na tela.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-136">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="fa8fd-137">Se você estiver interessado apenas no sucesso ou na falha do teste, isso pode não ser importante.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-137">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="fa8fd-138">Se preferir ver os detalhes completos dos dados retornados, canalize a saída para o cmdlet Format-List ao executar o teste:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-138">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="fa8fd-139">Isso exibirá a saída em um formato mais amigável para leitores:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-139">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="fa8fd-140">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="fa8fd-140">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="fa8fd-141">MatchingRule: Descrição =; Padrão = ^ ( \\ d {11} ) $; Conversão = + $1;</span><span class="sxs-lookup"><span data-stu-id="fa8fd-141">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="fa8fd-142">Name = prefix All; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="fa8fd-142">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="fa8fd-143">FirsMatchingRoute: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="fa8fd-143">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="fa8fd-144">MatchingUsage: local</span><span class="sxs-lookup"><span data-stu-id="fa8fd-144">MatchingUsage : Local</span></span>

<span data-ttu-id="fa8fd-145">Se o teste falhar, Test-CsVoiceUser retornará um conjunto vazio de valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-145">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="fa8fd-146">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="fa8fd-146">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="fa8fd-147">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="fa8fd-147">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fa8fd-148">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="fa8fd-148">Reasons why the test might have failed</span></span>

<span data-ttu-id="fa8fd-149">Há várias razões pelas quais o cmdlet Test-CsVoiceUser pode falhar: Talvez não haja uma regra de normalização que possa traduzir o número de telefone fornecido.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-149">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="fa8fd-150">Pode haver problemas com a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-150">There could be problems with the voice route.</span></span> <span data-ttu-id="fa8fd-151">Pode haver um problema de configuração com o plano de discagem atribuído ao usuário em questão.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-151">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="fa8fd-152">Por isso, talvez você queira incluir o parâmetro Verbose quando estiver executando o cmdlet Test-CsVoiceUser:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-152">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="fa8fd-153">Quando o cmdlet verboso for incluído, Test-CsVoiceUser emitirá uma conta detalhada de todas as etapas adotadas ao conduzir suas verificações.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-153">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="fa8fd-154">Por exemplo, você pode ver etapas semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="fa8fd-154">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="fa8fd-155">VERBOse: Localizando usuário com identidade "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="fa8fd-155">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="fa8fd-156">VERBOse: carregando o plano de discagem: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="fa8fd-156">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="fa8fd-157">Essas informações adicionais podem fornecer dicas sobre as etapas que você pode tomar para identificar a causa da falha.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-157">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="fa8fd-158">Por exemplo, a saída detalhada mostrada aqui diz que o usuário sendo testado recebeu o plano de discagem RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-158">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="fa8fd-159">Se o teste falhar, uma próxima etapa lógica será verificar se o RedmondDialPlan pode traduzir o número de telefone fornecido.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-159">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fa8fd-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="fa8fd-160">See Also</span></span>


[<span data-ttu-id="fa8fd-161">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="fa8fd-161">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

