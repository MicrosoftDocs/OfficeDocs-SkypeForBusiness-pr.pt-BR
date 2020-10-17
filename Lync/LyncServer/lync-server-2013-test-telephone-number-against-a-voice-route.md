---
title: 'Lync Server 2013: testar número de telefone em uma rota de voz'
description: 'Lync Server 2013: teste o número de telefone em uma rota de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789f4a538a992a72abf61f4c1fbdb98370f2e643
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563387"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="9e7db-103">Testar número de telefone em uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e7db-103">Test telephone number against a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e7db-104">_**Última modificação do tópico:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9e7db-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e7db-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="9e7db-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9e7db-106">Mensal</span><span class="sxs-lookup"><span data-stu-id="9e7db-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e7db-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="9e7db-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9e7db-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e7db-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e7db-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="9e7db-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9e7db-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9e7db-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9e7db-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="9e7db-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="9e7db-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9e7db-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9e7db-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e7db-113">Description</span></span>

<span data-ttu-id="9e7db-114">As rotas de voz trabalham juntas com políticas de voz para ajudar a rotear chamadas do Enterprise Voice para a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="9e7db-114">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="9e7db-115">Cada rota de voz inclui uma expressão regular (um padrão de número) que identifica os números de telefone que serão roteados por meio de uma determinada rota de voz: a rota será capaz de lidar com os números de telefone que correspondam a essa expressão regular.</span><span class="sxs-lookup"><span data-stu-id="9e7db-115">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="9e7db-116">Por exemplo, uma rota de voz pode ter uma expressão regular que permite manipular qualquer número de 10 dígitos.</span><span class="sxs-lookup"><span data-stu-id="9e7db-116">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="9e7db-117">Isso significa que a rota seria capaz de lidar com um número de telefone como este:</span><span class="sxs-lookup"><span data-stu-id="9e7db-117">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="9e7db-118">2065551219</span><span class="sxs-lookup"><span data-stu-id="9e7db-118">2065551219</span></span>

<span data-ttu-id="9e7db-119">A rota não seria capaz de lidar com um dos dois números a seguir, que não tem 10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="9e7db-119">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="9e7db-120">5551219</span><span class="sxs-lookup"><span data-stu-id="9e7db-120">5551219</span></span>

  - <span data-ttu-id="9e7db-121">12065551219</span><span class="sxs-lookup"><span data-stu-id="9e7db-121">12065551219</span></span>

<span data-ttu-id="9e7db-122">O cmdlet Test-CsVoiceRoute verifica se uma determinada rota de voz pode rotear um número de telefone especificado.</span><span class="sxs-lookup"><span data-stu-id="9e7db-122">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9e7db-123">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="9e7db-123">Running the test</span></span>

<span data-ttu-id="9e7db-124">Verificar a capacidade de uma rota de voz de rotear um número de telefone especificado é um processo de duas etapas.</span><span class="sxs-lookup"><span data-stu-id="9e7db-124">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="9e7db-125">Primeiro é necessário usar o cmdlet Get-CsVoiceRoute para retornar uma instância dessa rota de voz e, em seguida, você precisa usar o cmdlet Test-CsVoiceRoute para verificar a capacidade da rota de lidar com o número de telefone de destino.</span><span class="sxs-lookup"><span data-stu-id="9e7db-125">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="9e7db-126">Por exemplo, este comando verifica se a rota de voz do RedmondVoiceRoute pode rotear o número de telefone 2065551219:</span><span class="sxs-lookup"><span data-stu-id="9e7db-126">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="9e7db-127">Observe que o número de telefone deve ser digitado, já que você espera que os usuários disquem esse número.</span><span class="sxs-lookup"><span data-stu-id="9e7db-127">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="9e7db-128">Por exemplo, se você não espera que os usuários incluam o código do país e o código de área ao discar, use uma sintaxe semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="9e7db-128">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="9e7db-129">Nesse caso, o número de destino deixa o código do país e o código de área.</span><span class="sxs-lookup"><span data-stu-id="9e7db-129">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="9e7db-130">Para usar um único comando para testar todas as rotas de voz em relação a um número de destino especificado, use uma sintaxe como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="9e7db-130">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="9e7db-131">Para obter mais informações, consulte a documentação de ajuda para o cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="9e7db-131">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9e7db-132">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="9e7db-132">Determining success or failure</span></span>

<span data-ttu-id="9e7db-133">Se a rota de voz pode rotear o número de telefone de destino, o cmdlet Test-CsVoiceRoute apenas retorna o valor true:</span><span class="sxs-lookup"><span data-stu-id="9e7db-133">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="9e7db-134">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="9e7db-134">MatchesPattern</span></span>

\--------------

<span data-ttu-id="9e7db-135">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="9e7db-135">True</span></span>

<span data-ttu-id="9e7db-136">Isso significa que a rota pode lidar com números semelhantes ao número de destino.</span><span class="sxs-lookup"><span data-stu-id="9e7db-136">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="9e7db-137">Se a rota de voz não puder lidar com o número de destino, Test-CsVoiceRoute retornará o valor false:</span><span class="sxs-lookup"><span data-stu-id="9e7db-137">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="9e7db-138">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="9e7db-138">MatchesPattern</span></span>

\--------------

<span data-ttu-id="9e7db-139">Falso</span><span class="sxs-lookup"><span data-stu-id="9e7db-139">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9e7db-140">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="9e7db-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="9e7db-141">Ao testar rotas de voz, "falha" é um termo relativo.</span><span class="sxs-lookup"><span data-stu-id="9e7db-141">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="9e7db-142">Nesse caso, não significa que a rota está de alguma forma "interrompida"; em vez disso, apenas significa que a rota não pode lidar com o número de destino.</span><span class="sxs-lookup"><span data-stu-id="9e7db-142">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="9e7db-143">Isso pode ocorrer porque a rota de voz foi configurada incorretamente.</span><span class="sxs-lookup"><span data-stu-id="9e7db-143">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="9e7db-144">Também pode significar que a rota nunca se destinava a lidar com números usando esse padrão.</span><span class="sxs-lookup"><span data-stu-id="9e7db-144">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="9e7db-145">Por exemplo, se você não deseja encaminhar chamadas para outros países em uma determinada rota, essa rota pode ser configurada para rejeitar todos os números de telefone que incluem um código de país.</span><span class="sxs-lookup"><span data-stu-id="9e7db-145">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="9e7db-146">Se Test-CsVoiceRoute retornar false quando você esperava retornar true, verifique se digitou o número de destino corretamente.</span><span class="sxs-lookup"><span data-stu-id="9e7db-146">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="9e7db-147">Se você tiver feito isso, use um comando semelhante a este para exibir o NumberPattern configurado para a rota:</span><span class="sxs-lookup"><span data-stu-id="9e7db-147">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e7db-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="9e7db-148">See Also</span></span>


[<span data-ttu-id="9e7db-149">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="9e7db-149">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

