---
title: 'Lync Server 2013: testar número de telefone em uma política de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a234419dc6f06ae9bdc8d7c198873bdc3c706701
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="ea3e1-102">Testar número de telefone em uma política de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea3e1-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea3e1-103">_**Última modificação do tópico:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="ea3e1-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3e1-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="ea3e1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ea3e1-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="ea3e1-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3e1-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="ea3e1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ea3e1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea3e1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3e1-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="ea3e1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ea3e1-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ea3e1-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="ea3e1-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ea3e1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ea3e1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="ea3e1-112">Description</span></span>

<span data-ttu-id="ea3e1-113">A capacidade de usuários do Enterprise Voice de fazer chamadas telefônicas de saída por meio das dobradiças da PSTN (rede telefônica pública comutada), em grande parte, em três coisas:</span><span class="sxs-lookup"><span data-stu-id="ea3e1-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="ea3e1-114">A política de voz atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="ea3e1-115">As rotas de voz usadas para rotear chamadas do Lync Server para a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="ea3e1-116">O uso do PSTN, uma propriedade do Lync Server que conecta uma política de voz a uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="ea3e1-117">O uso do PSTN é especialmente importante: é a propriedade que conecta uma política de voz a uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="ea3e1-118">(Uma política de voz e uma rota de voz são consideradas conectadas se tiverem pelo menos um uso de PSTN em comum). As políticas de voz podem ser configuradas sem a especificação de um uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="ea3e1-119">Nesse caso, os usuários que receberam essa política não poderão fazer chamadas de saída na rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="ea3e1-120">Da mesma forma, as rotas de voz que não têm pelo menos um uso PSTN especificado não poderão rotear as chamadas para a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="ea3e1-121">O cmdlet Test-CsVoicePolicy verifica se uma determinada política de voz tem um uso de PSTN e se o uso é compartilhado por pelo menos uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="ea3e1-122">Se a verificação executada por Test-CsVoicePolicy tiver êxito, o cmdlet relatará o nome da primeira rota de voz válida que encontrará e também o nome do uso de PSTN que conecta a política à rota.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ea3e1-123">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="ea3e1-123">Running the test</span></span>

<span data-ttu-id="ea3e1-124">Para executar o cmdlet Test-CsVoicePolicy, primeiro você deve usar o cmdlet Get-CsVoicePolicy recuperar uma instância da política de voz a ser testada; essa instância deve então ser canalizada para Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="ea3e1-125">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ea3e1-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="ea3e1-126">Observe que esse comando, que não usa Get-CsVoicePolicy para recuperar uma instância de política de voz, falhará:</span><span class="sxs-lookup"><span data-stu-id="ea3e1-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="ea3e1-127">Se quiser verificar todas as políticas de voz em relação a um número de telefone específico, use um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="ea3e1-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="ea3e1-128">Observe que o TargetNumber deve ser especificado usando o formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="ea3e1-129">Test-CsVoicePolicy não tentará normalizar ou traduzir números de telefone no formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="ea3e1-130">Para obter mais informações, consulte a documentação de ajuda para o cmdlet Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ea3e1-131">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="ea3e1-131">Determining success or failure</span></span>

<span data-ttu-id="ea3e1-132">Se a política de voz puder encontrar uma rota de voz correspondente e um uso de PSTN correspondente, tanto a rota quanto o uso serão exibidos na tela:</span><span class="sxs-lookup"><span data-stu-id="ea3e1-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="ea3e1-133">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="ea3e1-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="ea3e1-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="ea3e1-134">\------------------ -------------</span></span>

<span data-ttu-id="ea3e1-135">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="ea3e1-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="ea3e1-136">Se uma rota de voz apropriada ou um uso de PSTN apropriado não puder ser encontrado, os valores de propriedade em branco serão exibidos na tela:</span><span class="sxs-lookup"><span data-stu-id="ea3e1-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="ea3e1-137">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="ea3e1-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="ea3e1-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="ea3e1-138">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ea3e1-139">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="ea3e1-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="ea3e1-140">Se Test-CsVoicePolicy não retornar uma correspondência que possa significar que a política de voz não compartilha um uso de PSTN com uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="ea3e1-141">Para verificar isso, use um cmdlet semelhante ao seguinte para verificar se os usos de PSTN foram atribuídos à política de voz:</span><span class="sxs-lookup"><span data-stu-id="ea3e1-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="ea3e1-142">Em seguida, execute este comando para determinar os usos de PSTN atribuídos a cada uma das suas rotas de voz:</span><span class="sxs-lookup"><span data-stu-id="ea3e1-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="ea3e1-143">Se você vir qualquer correspondência (ou seja, se vir uma ou mais rotas de voz que compartilham pelo menos um uso de PSTN com sua política de voz), deverá executar o cmdlet Test-CsVoiceRoute para verificar se a rota de voz pode discar o número de telefone fornecido.</span><span class="sxs-lookup"><span data-stu-id="ea3e1-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea3e1-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="ea3e1-144">See Also</span></span>


[<span data-ttu-id="ea3e1-145">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="ea3e1-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

