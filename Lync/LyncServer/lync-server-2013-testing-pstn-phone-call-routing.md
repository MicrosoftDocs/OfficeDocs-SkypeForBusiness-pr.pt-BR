---
title: 'Lync Server 2013: testar roteamento de chamadas telefônicas PSTN'
description: 'Lync Server 2013: testar roteamento de chamadas telefônicas PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da931b43176932a9b6781fa27318e83e6994548c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556267"
---
# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="10d29-103">Testando o roteamento de chamadas telefônicas PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10d29-103">Testing PSTN phone call routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10d29-104">_**Última modificação do tópico:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="10d29-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10d29-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="10d29-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="10d29-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="10d29-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d29-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="10d29-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="10d29-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10d29-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d29-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="10d29-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="10d29-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="10d29-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="10d29-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsInterTrunkRouting</strong> .</span><span class="sxs-lookup"><span data-stu-id="10d29-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="10d29-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="10d29-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="10d29-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="10d29-113">Description</span></span>

<span data-ttu-id="10d29-114">O cmdlet **Test-CsInterTrunkRouting** verifica se as chamadas podem ser roteadas de um SIP para outro.</span><span class="sxs-lookup"><span data-stu-id="10d29-114">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="10d29-115">Para fazer isso, o cmdlet recebe um número de telefone e uma configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="10d29-115">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="10d29-116">**Test-CsInterTrunkRouting** irá reportar as rotas de correspondência e os usos de PSTN correspondentes para o número especificado.</span><span class="sxs-lookup"><span data-stu-id="10d29-116">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="10d29-117">Observe que as chamadas só poderão ser roteadas entre troncos se os troncos tiverem um padrão numérico que corresponda ao número de telefone especificado e somente se os troncos compartilharem pelo menos um uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="10d29-117">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="10d29-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="10d29-118">Running the test</span></span>

<span data-ttu-id="10d29-119">Os comandos mostrados abaixo retornam as rotas correspondentes e os usos de telefone correspondentes que permitem que os usuários liguem para o número de telefone 1-206-555-1219 usando as definições de configuração de tronco para o site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="10d29-119">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="10d29-120">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="10d29-120">Determining success or failure</span></span>

<span data-ttu-id="10d29-121">Se as chamadas puderem ser encaminhadas de um SIP para outro, você receberá uma saída semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="10d29-121">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="10d29-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="10d29-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="10d29-123">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="10d29-123">\------------------ ------------- --------------</span></span>

<span data-ttu-id="10d29-124">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="10d29-124">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="10d29-125">Se o teste não tiver êxito, você receberá uma saída semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="10d29-125">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="10d29-126">Test-CsInterTrunkRouting: não é possível processar a transformação de argumento no parâmetro</span><span class="sxs-lookup"><span data-stu-id="10d29-126">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="10d29-127">"TrunkConfiguration".</span><span class="sxs-lookup"><span data-stu-id="10d29-127">'TrunkConfiguration'.</span></span> <span data-ttu-id="10d29-128">TrunkConfigurationsetting inválido (parâmetro).</span><span class="sxs-lookup"><span data-stu-id="10d29-128">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="10d29-129">Especificar um</span><span class="sxs-lookup"><span data-stu-id="10d29-129">Specify a</span></span>

<span data-ttu-id="10d29-130">configuração válida (parâmetro) e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="10d29-130">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="10d29-131">Na linha: 1 caractere: 79</span><span class="sxs-lookup"><span data-stu-id="10d29-131">At line:1 char:79</span></span>

<span data-ttu-id="10d29-132">\+ Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="10d29-132">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="10d29-133">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="10d29-133">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="10d29-134">\+ CategoryInfo: InvalidData: (:) \[ Test-CsInterTrunkRouting \] , par</span><span class="sxs-lookup"><span data-stu-id="10d29-134">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="10d29-135">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="10d29-135">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="10d29-136">\+ FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="10d29-136">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="10d29-137">TC. Management. Voice. cmdlets. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="10d29-137">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="10d29-138">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="10d29-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="10d29-139">Aqui estão alguns motivos comuns pelos quais **Test-CsInterTrunkRouting** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="10d29-139">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="10d29-140">Você especificou parâmetros inválidos.</span><span class="sxs-lookup"><span data-stu-id="10d29-140">You specified invalid parameters.</span></span> <span data-ttu-id="10d29-141">O tronco pode não estar corretamente configurado e o número de destino especificado pode estar incorreto ou inválido.</span><span class="sxs-lookup"><span data-stu-id="10d29-141">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10d29-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="10d29-142">See Also</span></span>


[<span data-ttu-id="10d29-143">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="10d29-143">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="10d29-144">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="10d29-144">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

