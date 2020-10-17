---
title: 'Lync Server 2013: testar número de telefone em uma política de voz'
description: 'Lync Server 2013: teste o número de telefone em uma política de voz.'
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
ms.openlocfilehash: 5a6523e7657bd4c30c23909bb02e2569b6067298
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548027"
---
# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="268d6-103">Testar número de telefone em uma política de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268d6-103">Test telephone number against a voice policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="268d6-104">_**Última modificação do tópico:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="268d6-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="268d6-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="268d6-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="268d6-106">Mensal</span><span class="sxs-lookup"><span data-stu-id="268d6-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="268d6-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="268d6-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="268d6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="268d6-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="268d6-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="268d6-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="268d6-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="268d6-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="268d6-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="268d6-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="268d6-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="268d6-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="268d6-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="268d6-113">Description</span></span>

<span data-ttu-id="268d6-114">A capacidade de usuários do Enterprise Voice de fazer chamadas telefônicas de saída por meio das dobradiças da PSTN (rede telefônica pública comutada), em grande parte, em três coisas:</span><span class="sxs-lookup"><span data-stu-id="268d6-114">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="268d6-115">A política de voz atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="268d6-115">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="268d6-116">As rotas de voz usadas para rotear chamadas do Lync Server para a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="268d6-116">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="268d6-117">O uso do PSTN, uma propriedade do Lync Server que conecta uma política de voz a uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="268d6-117">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="268d6-118">O uso do PSTN é especialmente importante: é a propriedade que conecta uma política de voz a uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="268d6-118">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="268d6-119">(Uma política de voz e uma rota de voz são consideradas conectadas se tiverem pelo menos um uso de PSTN em comum). As políticas de voz podem ser configuradas sem a especificação de um uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="268d6-119">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="268d6-120">Nesse caso, os usuários que receberam essa política não poderão fazer chamadas de saída na rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="268d6-120">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="268d6-121">Da mesma forma, as rotas de voz que não têm pelo menos um uso PSTN especificado não poderão rotear as chamadas para a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="268d6-121">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="268d6-122">O cmdlet Test-CsVoicePolicy verifica se uma determinada política de voz tem um uso de PSTN e se o uso é compartilhado por pelo menos uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="268d6-122">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="268d6-123">Se a verificação for executada por Test-CsVoicePolicy tiver êxito, o cmdlet relatará o nome da primeira rota de voz válida que encontrará e também o nome do uso de PSTN que conecta a política à rota.</span><span class="sxs-lookup"><span data-stu-id="268d6-123">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="268d6-124">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="268d6-124">Running the test</span></span>

<span data-ttu-id="268d6-125">Para executar o cmdlet Test-CsVoicePolicy você deve primeiro usar o cmdlet Get-CsVoicePolicy recuperar uma instância da política de voz a ser testada; essa instância deve então ser canalizada para Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="268d6-125">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="268d6-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="268d6-126">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="268d6-127">Observe que esse comando, que não usa Get-CsVoicePolicy para recuperar uma instância de política de voz, falhará:</span><span class="sxs-lookup"><span data-stu-id="268d6-127">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="268d6-128">Se quiser verificar todas as políticas de voz em relação a um número de telefone específico, use um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="268d6-128">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="268d6-129">Observe que o TargetNumber deve ser especificado usando o formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="268d6-129">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="268d6-130">Test-CsVoicePolicy não tentará normalizar ou traduzir números de telefone no formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="268d6-130">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="268d6-131">Para obter mais informações, consulte a documentação de ajuda para o cmdlet Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="268d6-131">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="268d6-132">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="268d6-132">Determining success or failure</span></span>

<span data-ttu-id="268d6-133">Se a política de voz puder encontrar uma rota de voz correspondente e um uso de PSTN correspondente, tanto a rota quanto o uso serão exibidos na tela:</span><span class="sxs-lookup"><span data-stu-id="268d6-133">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="268d6-134">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="268d6-134">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="268d6-135">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="268d6-135">\------------------ -------------</span></span>

<span data-ttu-id="268d6-136">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="268d6-136">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="268d6-137">Se uma rota de voz apropriada ou um uso de PSTN apropriado não puder ser encontrado, os valores de propriedade em branco serão exibidos na tela:</span><span class="sxs-lookup"><span data-stu-id="268d6-137">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="268d6-138">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="268d6-138">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="268d6-139">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="268d6-139">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="268d6-140">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="268d6-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="268d6-141">Se Test-CsVoicePolicy não retornar uma correspondência que possa significar que a política de voz não compartilha um uso de PSTN com uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="268d6-141">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="268d6-142">Para verificar isso, use um cmdlet semelhante ao seguinte para verificar se os usos de PSTN foram atribuídos à política de voz:</span><span class="sxs-lookup"><span data-stu-id="268d6-142">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="268d6-143">Em seguida, execute este comando para determinar os usos de PSTN atribuídos a cada uma das suas rotas de voz:</span><span class="sxs-lookup"><span data-stu-id="268d6-143">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="268d6-144">Se você vir qualquer correspondência (ou seja, se vir uma ou mais rotas de voz que compartilham pelo menos um uso de PSTN com sua política de voz), deverá executar o cmdlet Test-CsVoiceRoute para verificar se a rota de voz pode discar o número de telefone fornecido.</span><span class="sxs-lookup"><span data-stu-id="268d6-144">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="268d6-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="268d6-145">See Also</span></span>


[<span data-ttu-id="268d6-146">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="268d6-146">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

