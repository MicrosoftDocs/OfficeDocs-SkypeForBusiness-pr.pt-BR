---
title: 'Lync Server 2013: testando o encaminhamento de chamadas telefônicas PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faa6bfe178397ab474c1bcd8edc21107faff8dc3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="0c57d-102">Testando o roteamento de chamadas telefônicas PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c57d-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c57d-103">_**Tópico da última modificação:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="0c57d-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c57d-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="0c57d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0c57d-105">Diário</span><span class="sxs-lookup"><span data-stu-id="0c57d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c57d-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="0c57d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0c57d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c57d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c57d-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="0c57d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0c57d-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0c57d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0c57d-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsInterTrunkRouting</strong> .</span><span class="sxs-lookup"><span data-stu-id="0c57d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="0c57d-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0c57d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0c57d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="0c57d-112">Description</span></span>

<span data-ttu-id="0c57d-113">O cmdlet **Test-CsInterTrunkRouting** verifica se as chamadas podem ser roteadas de um SIP para outro.</span><span class="sxs-lookup"><span data-stu-id="0c57d-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="0c57d-114">Para fazer isso, o cmdlet recebe um número de telefone e uma configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="0c57d-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="0c57d-115">**Test-CsInterTrunkRouting** reportará os roteiros correspondentes e os usos de PSTN correspondentes para o número especificado.</span><span class="sxs-lookup"><span data-stu-id="0c57d-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="0c57d-116">Observe que as chamadas podem ser roteadas entre troncos apenas se os troncos possuem um padrão de número que corresponde ao número de telefone especificado e apenas se os troncos compartilham pelo menos um uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="0c57d-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0c57d-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="0c57d-117">Running the test</span></span>

<span data-ttu-id="0c57d-118">Os comandos exibidos abaixo retornam as rotas correspondentes e os usos de telefone correspondentes que permitem que os usuários chamem o número de telefone 1-206-555-1219 usando as configurações de tronco de configuração para o site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="0c57d-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0c57d-119">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="0c57d-119">Determining success or failure</span></span>

<span data-ttu-id="0c57d-120">Se as chamadas puderem ser roteadas de um SIP para outro, você receberá uma saída semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="0c57d-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="0c57d-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="0c57d-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="0c57d-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="0c57d-122"></span></span>

<span data-ttu-id="0c57d-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="0c57d-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="0c57d-124">Se o teste não for bem-sucedido, você receberá uma saída semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="0c57d-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="0c57d-125">Test-CsInterTrunkRouting: não é possível processar a transformação do argumento no parâmetro</span><span class="sxs-lookup"><span data-stu-id="0c57d-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="0c57d-126">'TrunkConfiguration'.</span><span class="sxs-lookup"><span data-stu-id="0c57d-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="0c57d-127">TrunkConfigurationsetting (parâmetro) inválido.</span><span class="sxs-lookup"><span data-stu-id="0c57d-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="0c57d-128">Especificar um</span><span class="sxs-lookup"><span data-stu-id="0c57d-128">Specify a</span></span>

<span data-ttu-id="0c57d-129">configuração válida (parâmetro) e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="0c57d-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="0c57d-130">Na linha: 1 caractere: 79</span><span class="sxs-lookup"><span data-stu-id="0c57d-130">At line:1 char:79</span></span>

<span data-ttu-id="0c57d-131">\+Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="0c57d-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="0c57d-132">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="0c57d-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="0c57d-133">\+CategoryInfo: InvalidData: (:) \[Test-CsInterTrunkRouting\], par</span><span class="sxs-lookup"><span data-stu-id="0c57d-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="0c57d-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="0c57d-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="0c57d-135">\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="0c57d-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="0c57d-136">TC. Management. Voice. cmdlets. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="0c57d-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0c57d-137">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="0c57d-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="0c57d-138">Aqui estão alguns motivos comuns pelos quais **Test-CsInterTrunkRouting** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="0c57d-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="0c57d-139">Você especificou parâmetros inválidos.</span><span class="sxs-lookup"><span data-stu-id="0c57d-139">You specified invalid parameters.</span></span> <span data-ttu-id="0c57d-140">O tronco pode não estar corretamente configurado e o número de destino especificado pode estar incorreto ou inválido.</span><span class="sxs-lookup"><span data-stu-id="0c57d-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c57d-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="0c57d-141">See Also</span></span>


[<span data-ttu-id="0c57d-142">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="0c57d-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="0c57d-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0c57d-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

