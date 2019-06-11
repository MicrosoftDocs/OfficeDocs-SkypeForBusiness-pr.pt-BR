---
title: 'Lync Server 2013: verificar a configuração de tronco em relação a um número de telefone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b667f43e430b5047f72e2d8352f57337f0849055
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="15bef-102">Verificar a configuração de tronco em relação a um número de telefone no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15bef-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15bef-103">_**Tópico da última modificação:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="15bef-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15bef-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="15bef-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="15bef-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="15bef-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15bef-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="15bef-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="15bef-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15bef-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15bef-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="15bef-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="15bef-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="15bef-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="15bef-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="15bef-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="15bef-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="15bef-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="15bef-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="15bef-112">Description</span></span>

<span data-ttu-id="15bef-113">Os troncos SIP conectam a rede do Lync Server Internal Enterprise Voice a qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="15bef-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="15bef-114">A rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="15bef-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="15bef-115">Um PBX IP-Public Branch Exchange (PBX).</span><span class="sxs-lookup"><span data-stu-id="15bef-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="15bef-116">Um controlador de borda de sessão (SBC).</span><span class="sxs-lookup"><span data-stu-id="15bef-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="15bef-117">O cmdlet Test-CsTrunkConfiguration verifica se um número de telefone (como discado por um usuário) pode ser convertido na rede E. 164 e roteado em um tronco SIP especificado.</span><span class="sxs-lookup"><span data-stu-id="15bef-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="15bef-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="15bef-118">Running the test</span></span>

<span data-ttu-id="15bef-119">Para executar o cmdlet Test-CsTrunkConfiguration, primeiro você deve usar o cmdlet Get-CsTrunkConfiguration para recuperar uma instância de suas configurações de tronco SIP; essa instância é então canalizada para Test-CsTrunkConfiguration:</span><span class="sxs-lookup"><span data-stu-id="15bef-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="15bef-120">Executar Test-CsTrunkConfiguration sem a primeira vez que Get-CsTrunkConfiguration não funcionará.</span><span class="sxs-lookup"><span data-stu-id="15bef-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="15bef-121">Por exemplo, esse comando falhará sem retornar nenhum dado:</span><span class="sxs-lookup"><span data-stu-id="15bef-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="15bef-122">Se você tiver várias coleções de configurações de configuração de tronco SIP, poderá usar um comando semelhante ao seguinte para, ao mesmo tempo, testar cada coleção com o mesmo número de telefone:</span><span class="sxs-lookup"><span data-stu-id="15bef-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="15bef-123">Para obter mais informações, consulte a documentação da ajuda para o cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="15bef-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="15bef-124">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="15bef-124">Determining success or failure</span></span>

<span data-ttu-id="15bef-125">Se Test-CsTrunkConfiguration puder fazer uma chamada para o número discado, o número de telefone traduzido (no formato E. 164) e a regra usada para traduzir esse número de telefone serão exibidos na tela:</span><span class="sxs-lookup"><span data-stu-id="15bef-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="15bef-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="15bef-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="15bef-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="15bef-127"></span></span>

<span data-ttu-id="15bef-128">\+12065551219 global/Redmond</span><span class="sxs-lookup"><span data-stu-id="15bef-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="15bef-129">Se o teste falhar, Test-CsTrunkConfiguration retornará valores de propriedade vazia:</span><span class="sxs-lookup"><span data-stu-id="15bef-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="15bef-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="15bef-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="15bef-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="15bef-131"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="15bef-132">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="15bef-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="15bef-133">Se Test-CsTrunkConfiguration não retornar uma coincidência que normalmente significa que as configurações de configuração de tronco que estão sendo testadas não têm uma regra de tradução de número de chamadas de saída capaz de converter o número discado para o formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="15bef-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="15bef-134">Para recuperar as regras de tradução atribuídas a uma coleção de definições de configuração de tronco, você pode usar uma sintaxe semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="15bef-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="15bef-135">Que retorna informações semelhantes para cada regra de Tradução:</span><span class="sxs-lookup"><span data-stu-id="15bef-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="15bef-136">Descrição: números de telefone sem um código de país ou código de área.</span><span class="sxs-lookup"><span data-stu-id="15bef-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="15bef-137">Padrão: ^\\+ (\\d\*) $</span><span class="sxs-lookup"><span data-stu-id="15bef-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="15bef-138">Nome: NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="15bef-138">Name : NoAreaCode</span></span>

<span data-ttu-id="15bef-139">Nesse ponto, você verifica o valor da propriedade Pattern (que é uma cadeia de caracteres de [expressão regular](http://go.microsoft.com/fwlink/?linkid=400464) ) para ver se alguma das regras de tradução está configurada para manipular o número discado.</span><span class="sxs-lookup"><span data-stu-id="15bef-139">At that point, you check the value of the Pattern property (which is a [regular expression](http://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="15bef-140">Caso contrário, você precisará alterar uma das regras existentes (Set-CsOutboundTranslationRule) ou usar o cmdlet New-CsOutboundTranslationRule para adicionar uma nova regra à coleção.</span><span class="sxs-lookup"><span data-stu-id="15bef-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15bef-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="15bef-141">See Also</span></span>


[<span data-ttu-id="15bef-142">Test-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="15bef-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

