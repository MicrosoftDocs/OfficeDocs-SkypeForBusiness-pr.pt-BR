---
title: 'Lync Server 2013: teste o número de telefone em uma rota de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed50971c9656d454a44eeee627de95c187ef008f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="e32a9-102">Teste o número de telefone em uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e32a9-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e32a9-103">_**Tópico da última modificação:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="e32a9-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e32a9-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="e32a9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e32a9-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="e32a9-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e32a9-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="e32a9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e32a9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e32a9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e32a9-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="e32a9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e32a9-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e32a9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e32a9-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="e32a9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="e32a9-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e32a9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e32a9-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e32a9-112">Description</span></span>

<span data-ttu-id="e32a9-113">As rotas de voz trabalham em conjunto com as políticas de voz para ajudar a rotear chamadas do Enterprise Voice para a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="e32a9-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="e32a9-114">Cada rota de voz inclui uma expressão regular (um padrão de número) que identifica os números de telefone que serão roteados por meio de uma determinada rota de voz: a rota será capaz de manipular os números de telefone correspondentes a essa expressão regular.</span><span class="sxs-lookup"><span data-stu-id="e32a9-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="e32a9-115">Por exemplo, uma rota de voz pode ter uma expressão regular que a permita manipular qualquer número de 10 dígitos.</span><span class="sxs-lookup"><span data-stu-id="e32a9-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="e32a9-116">Isso significa que a rota seria capaz de manipular um número de telefone como este:</span><span class="sxs-lookup"><span data-stu-id="e32a9-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="e32a9-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="e32a9-117">2065551219</span></span>

<span data-ttu-id="e32a9-118">A rota não seria capaz de manipular um dos dois números a seguir, e nenhum deles tem 10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="e32a9-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="e32a9-119">5551219</span><span class="sxs-lookup"><span data-stu-id="e32a9-119">5551219</span></span>

  - <span data-ttu-id="e32a9-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="e32a9-120">12065551219</span></span>

<span data-ttu-id="e32a9-121">O cmdlet Test-CsVoiceRoute verifica se uma determinada rota de voz pode direcionar um número de telefone especificado.</span><span class="sxs-lookup"><span data-stu-id="e32a9-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e32a9-122">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="e32a9-122">Running the test</span></span>

<span data-ttu-id="e32a9-123">Verificar se a capacidade de uma rota de voz para direcionar um número de telefone especificado é um processo de duas etapas.</span><span class="sxs-lookup"><span data-stu-id="e32a9-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="e32a9-124">Primeiro, você precisa usar o cmdlet Get-CsVoiceRoute para retornar uma instância dessa rota de voz e, em seguida, usar o cmdlet Test-CsVoiceRoute para verificar a capacidade dessa rota para manipular o número de telefone de destino.</span><span class="sxs-lookup"><span data-stu-id="e32a9-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="e32a9-125">Por exemplo, esse comando verifica se a rota de voz RedmondVoiceRoute pode direcionar o número de telefone 2065551219:</span><span class="sxs-lookup"><span data-stu-id="e32a9-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="e32a9-126">Observe que o número de telefone deve ser digitado, pois você espera que os usuários disquem esse número.</span><span class="sxs-lookup"><span data-stu-id="e32a9-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="e32a9-127">Por exemplo, se você não espera que os usuários incluam o código do país e o código de área ao discar, use uma sintaxe semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="e32a9-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="e32a9-128">Nesse caso, o número de destino deixará o código de país e o código de área.</span><span class="sxs-lookup"><span data-stu-id="e32a9-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="e32a9-129">Para usar um único comando para testar todas as rotas de voz em relação a um número de destino especificado, use a sintaxe como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="e32a9-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="e32a9-130">Para obter mais informações, consulte a documentação da ajuda para o cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="e32a9-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e32a9-131">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="e32a9-131">Determining success or failure</span></span>

<span data-ttu-id="e32a9-132">Se a rota de voz puder direcionar o número de telefone de destino, o cmdlet Test-CsVoiceRoute apenas retornará o valor true:</span><span class="sxs-lookup"><span data-stu-id="e32a9-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="e32a9-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="e32a9-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="e32a9-134">True</span><span class="sxs-lookup"><span data-stu-id="e32a9-134">True</span></span>

<span data-ttu-id="e32a9-135">Isso significa que a rota pode manipular números semelhantes ao número de destino.</span><span class="sxs-lookup"><span data-stu-id="e32a9-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="e32a9-136">Se a rota de voz não puder manipular o número de destino, teste-CsVoiceRoute retornará o valor false:</span><span class="sxs-lookup"><span data-stu-id="e32a9-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="e32a9-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="e32a9-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="e32a9-138">False</span><span class="sxs-lookup"><span data-stu-id="e32a9-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e32a9-139">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="e32a9-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="e32a9-140">Ao testar as rotas de voz, "falha" é um termo relativo.</span><span class="sxs-lookup"><span data-stu-id="e32a9-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="e32a9-141">Nesse caso, não significa que a rota está de alguma forma "interrompida;" em vez disso, significa que a rota não pode manipular o número de destino.</span><span class="sxs-lookup"><span data-stu-id="e32a9-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="e32a9-142">Isso pode ser porque a rota de voz foi configurada incorretamente.</span><span class="sxs-lookup"><span data-stu-id="e32a9-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="e32a9-143">Também pode significar que a rota nunca se destina a manipular números usando esse padrão.</span><span class="sxs-lookup"><span data-stu-id="e32a9-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="e32a9-144">Por exemplo, se você não quiser direcionar chamadas para outros países em uma determinada rota, essa rota pode ser configurada para rejeitar todos os números de telefone que incluem um código de país.</span><span class="sxs-lookup"><span data-stu-id="e32a9-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="e32a9-145">Se Test-CsVoiceRoute retornar false quando você espera retornar true, verifique se digitou o número de destino corretamente.</span><span class="sxs-lookup"><span data-stu-id="e32a9-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="e32a9-146">Se você fez isso, use um comando semelhante a este para exibir o NumberPattern configurado para a rota:</span><span class="sxs-lookup"><span data-stu-id="e32a9-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e32a9-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="e32a9-147">See Also</span></span>


[<span data-ttu-id="e32a9-148">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="e32a9-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

