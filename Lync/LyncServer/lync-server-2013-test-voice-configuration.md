---
title: 'Lync Server 2013: testar configuração de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2894d61a4dabd174315e24a225392bde7a893300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="cbca1-102">Testar a configuração de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbca1-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbca1-103">_**Última modificação do tópico:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="cbca1-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbca1-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="cbca1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="cbca1-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="cbca1-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbca1-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="cbca1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="cbca1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbca1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbca1-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="cbca1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="cbca1-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cbca1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="cbca1-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cbca1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="cbca1-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cbca1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="cbca1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="cbca1-112">Description</span></span>

<span data-ttu-id="cbca1-113">O Lync Server inclui vários cmdlets do Windows PowerShell (como Test-CsVoiceRoute e Test-CsVoicePolicy, Test-CsTrunkConfiguration) que permitem verificar se as partes individuais de sua infraestrutura do Enterprise Voice – rotas de voz, voz as políticas, troncos SIP – estão funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="cbca1-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="cbca1-114">Embora seja importante com o Enterprise Voice que todas as partes individuais funcionem: é possível ter uma rota de voz válida, uma política de voz válida e um tronco SIP válido, mas ainda assim os usuários não podem fazer ou receber chamadas telefônicas.</span><span class="sxs-lookup"><span data-stu-id="cbca1-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="cbca1-115">Por isso, o Lync Server também oferece a capacidade de criar configurações de teste de voz.</span><span class="sxs-lookup"><span data-stu-id="cbca1-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="cbca1-116">As configurações de teste de voz representam cenários comuns do Enterprise Voice: você pode especificar coisas como uma rota de voz, uma política de voz e um plano de discagem e, em seguida, verificar se esses itens individuais podem trabalhar juntos para fornecer serviço de telefone.</span><span class="sxs-lookup"><span data-stu-id="cbca1-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="cbca1-117">Além disso, você pode validar suas expectativas em um determinado cenário.</span><span class="sxs-lookup"><span data-stu-id="cbca1-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="cbca1-118">Por exemplo, suponha que você espera que a combinação de plano de discagem A e a política de voz B resulte em chamadas sendo roteadas pela rota de voz C. Você pode inserir a rota de voz C como ExpectedRoute.</span><span class="sxs-lookup"><span data-stu-id="cbca1-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="cbca1-119">Quando você executar o teste, se a rota de voz C não for empregada, o teste será marcado como tendo falhado.</span><span class="sxs-lookup"><span data-stu-id="cbca1-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="cbca1-120">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="cbca1-120">Running the test</span></span>

<span data-ttu-id="cbca1-121">Antes de testar as coleções de configuração de voz usando o Windows PowerShell, você deve primeiro usar o cmdlet Get-CsVoiceTestConfiguration para recuperar uma instância dessas definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="cbca1-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="cbca1-122">Essa instância deve então ser canalizada para o Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cbca1-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="cbca1-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cbca1-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="cbca1-124">Para validar todas as definições de configuração de teste de voz ao mesmo tempo, use este comando:</span><span class="sxs-lookup"><span data-stu-id="cbca1-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="cbca1-125">Para obter mais informações, consulte a documentação de ajuda para o cmdlet Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cbca1-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="cbca1-126">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="cbca1-126">Determining success or failure</span></span>

<span data-ttu-id="cbca1-127">O cmdlet Test-CsVoiceTestConfiguration relata se um teste falhou ou teve êxito e fornece informações adicionais sobre cada teste bem-sucedido, como a regra de conversão, a rota de voz e o uso de PSTN usados para concluir a tarefa:</span><span class="sxs-lookup"><span data-stu-id="cbca1-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="cbca1-128">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="cbca1-128">Result:             Success</span></span>

<span data-ttu-id="cbca1-129">TranslatedNumber: + 15551234</span><span class="sxs-lookup"><span data-stu-id="cbca1-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="cbca1-130">MatchingRule: Descrição =; Padrão = ^ (\\d{4}) $; Tradução = + 1\\d; Name = teste; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="cbca1-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="cbca1-131">FirstMatchingRoute: site: Redmond</span><span class="sxs-lookup"><span data-stu-id="cbca1-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="cbca1-132">MatchingUsage: local</span><span class="sxs-lookup"><span data-stu-id="cbca1-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="cbca1-133">Se o teste falhar, o resultado será relatado como falha:</span><span class="sxs-lookup"><span data-stu-id="cbca1-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="cbca1-134">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="cbca1-134">Result:             Fail</span></span>

<span data-ttu-id="cbca1-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="cbca1-135">TranslatedNumber:</span></span>   

<span data-ttu-id="cbca1-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="cbca1-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="cbca1-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="cbca1-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="cbca1-138">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="cbca1-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="cbca1-139">Como o teste de configuração de teste de voz testa vários itens diferentes, incluindo políticas de voz, planos de discagem, rotas de voz e assim por diante, há vários fatores diferentes que podem resultar em um teste com falha.</span><span class="sxs-lookup"><span data-stu-id="cbca1-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="cbca1-140">Se um teste falhar, sua primeira etapa deve ser revisar as definições de configuração por conta própria usando o cmdlet Get-CsVoiceTestConfiguration:</span><span class="sxs-lookup"><span data-stu-id="cbca1-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="cbca1-141">Se as configurações parecem estar configuradas corretamente, execute o teste novamente, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="cbca1-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="cbca1-142">O parâmetro Verbose fornecerá uma conta passo a passo de cada ação tomada por Test-CsVoiceTestConfiguration, conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="cbca1-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="cbca1-143">VERBOse: carregando o plano de discagem: "global"</span><span class="sxs-lookup"><span data-stu-id="cbca1-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="cbca1-144">VERBOse: carregando política de voz: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="cbca1-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="cbca1-145">Esta conta passo a passo pode fornecer uma pista útil para onde o teste realmente falhou.</span><span class="sxs-lookup"><span data-stu-id="cbca1-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="cbca1-146">Caso contrário, você poderá usar outros cmdlets do Windows PowerShell (como Test-CsVoicePolicy) e começar metodicamente a verificar os componentes individuais que estão incluídos nas definições de configuração do teste de voz.</span><span class="sxs-lookup"><span data-stu-id="cbca1-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="cbca1-147">Além disso, esteja ciente de que é possível que um teste seja capaz de rotear uma chamada e ainda seja marcado como uma falha; Isso pode ocorrer se você inserir valores para ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage, e qualquer uma dessas expectativas não for atendida.</span><span class="sxs-lookup"><span data-stu-id="cbca1-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="cbca1-148">Por exemplo, suponha que você insira a rota de voz C como rota de voz esperada, mas o teste realmente conclui a chamada usando a rota de voz D. Nesse caso, o teste será marcado como Failed porque a rota de voz esperada não foi usada.</span><span class="sxs-lookup"><span data-stu-id="cbca1-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="cbca1-149">Se um teste falhar, você poderá remover os valores de ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage e, em seguida, executar novamente o teste.</span><span class="sxs-lookup"><span data-stu-id="cbca1-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="cbca1-150">Isso ajudará você a determinar se a falha ocorreu porque a chamada não pôde ser concluída ou porque você espera uma coisa e realmente recebeu outra.</span><span class="sxs-lookup"><span data-stu-id="cbca1-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cbca1-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="cbca1-151">See Also</span></span>


[<span data-ttu-id="cbca1-152">Test-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="cbca1-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

