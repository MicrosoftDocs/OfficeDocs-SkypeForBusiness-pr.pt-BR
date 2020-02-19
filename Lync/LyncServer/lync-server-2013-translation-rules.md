---
title: 'Lync Server 2013: regras de conversão'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 088657d530224288a9ffabbfa1644d0fea6796e7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="eedfb-102">Regras de conversão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eedfb-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eedfb-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="eedfb-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="eedfb-104">Lync Server 2013 Enterprise Voice requer que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E. 164 com o objetivo de executar a pesquisa de número reverso (RNL).</span><span class="sxs-lookup"><span data-stu-id="eedfb-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="eedfb-105">No Microsoft Lync Server 2010, as regras de conversão têm suporte apenas para números chamados.</span><span class="sxs-lookup"><span data-stu-id="eedfb-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="eedfb-106">Novo no Microsoft Lync Server 2013, as regras de conversão também têm suporte para números de chamada.</span><span class="sxs-lookup"><span data-stu-id="eedfb-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="eedfb-107">O *par de tronco* (isto é, o troco de gateway, PBX ou SIP associado) pode exigir que os números estejam no formato de discagem local.</span><span class="sxs-lookup"><span data-stu-id="eedfb-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="eedfb-108">Para converter os números do formato E.164 em um formato de discagem local, você pode definir uma ou mais regras de conversão para manipular a URI da solicitação antes de roteá-la para o ponto do tronco.</span><span class="sxs-lookup"><span data-stu-id="eedfb-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="eedfb-109">Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.</span><span class="sxs-lookup"><span data-stu-id="eedfb-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="eedfb-110">Executando a conversão da rota de saída no servidor, você pode reduzir os requisitos de configuração em cada par de tronco individual para converter os números de telefone em um formato de discagem.</span><span class="sxs-lookup"><span data-stu-id="eedfb-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="eedfb-111">Quando você planeja quais gateways e quantos gateways estão associados a um cluster do servidor de mediação específico, pode ser útil agrupar os pares de tronco com requisitos de discagem locais semelhantes.</span><span class="sxs-lookup"><span data-stu-id="eedfb-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="eedfb-112">Isso pode reduzir o número de regras de conversão necessárias e o tempo necessário para gravá-las.</span><span class="sxs-lookup"><span data-stu-id="eedfb-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eedfb-113">A associação de uma ou mais regras de conversão a uma configuração de tronco do Enterprise Voice deve ser usada como alternativa à configuração de regras de conversão no par de tronco.</span><span class="sxs-lookup"><span data-stu-id="eedfb-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="eedfb-114">Não associe as regras de conversão a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de conversão no par de tronco, pois as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="eedfb-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="eedfb-115">Exemplo de regras de conversão</span><span class="sxs-lookup"><span data-stu-id="eedfb-115">Example Translation Rules</span></span>

<span data-ttu-id="eedfb-116">Os exemplos a seguir de regras de conversão mostram como você pode desenvolver as regras no servidor para converter números do formato E.164 para um formato local para o par de tronco.</span><span class="sxs-lookup"><span data-stu-id="eedfb-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="eedfb-117">Para obter detalhes sobre como implementar regras de conversão, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="eedfb-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eedfb-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="eedfb-118">Description</span></span></th>
<th><span data-ttu-id="eedfb-119">Dígitos iniciais</span><span class="sxs-lookup"><span data-stu-id="eedfb-119">Starting Digits</span></span></th>
<th><span data-ttu-id="eedfb-120">Comprimento</span><span class="sxs-lookup"><span data-stu-id="eedfb-120">Length</span></span></th>
<th><span data-ttu-id="eedfb-121">Dígitos a serem removidos</span><span class="sxs-lookup"><span data-stu-id="eedfb-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="eedfb-122">Dígitos a serem adicionados</span><span class="sxs-lookup"><span data-stu-id="eedfb-122">Digits to Add</span></span></th>
<th><span data-ttu-id="eedfb-123">Padrão de correspondência</span><span class="sxs-lookup"><span data-stu-id="eedfb-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="eedfb-124">Tradução</span><span class="sxs-lookup"><span data-stu-id="eedfb-124">Translation</span></span></th>
<th><span data-ttu-id="eedfb-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="eedfb-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eedfb-126">Discagem convencional de longa distância nos EUA</span><span class="sxs-lookup"><span data-stu-id="eedfb-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="eedfb-127">(retirar o '+')</span><span class="sxs-lookup"><span data-stu-id="eedfb-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="eedfb-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="eedfb-128">+1</span></span></p></td>
<td><p><span data-ttu-id="eedfb-129">Exatamente 12</span><span class="sxs-lookup"><span data-stu-id="eedfb-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="eedfb-130">1</span><span class="sxs-lookup"><span data-stu-id="eedfb-130">1</span></span></p></td>
<td><p><span data-ttu-id="eedfb-131">,0</span><span class="sxs-lookup"><span data-stu-id="eedfb-131">0</span></span></p></td>
<td><p><span data-ttu-id="eedfb-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="eedfb-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="eedfb-133">$1</span><span class="sxs-lookup"><span data-stu-id="eedfb-133">$1</span></span></p></td>
<td><p><span data-ttu-id="eedfb-134">+14255551010 se torna 14255551010</span><span class="sxs-lookup"><span data-stu-id="eedfb-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedfb-135">Discagem de longa distância internacional dos EUA</span><span class="sxs-lookup"><span data-stu-id="eedfb-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="eedfb-136">(retirar '+' e adicionar 011)</span><span class="sxs-lookup"><span data-stu-id="eedfb-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="eedfb-137">Pelo menos 11</span><span class="sxs-lookup"><span data-stu-id="eedfb-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="eedfb-138">1</span><span class="sxs-lookup"><span data-stu-id="eedfb-138">1</span></span></p></td>
<td><p><span data-ttu-id="eedfb-139">00</span><span class="sxs-lookup"><span data-stu-id="eedfb-139">011</span></span></p></td>
<td><p><span data-ttu-id="eedfb-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="eedfb-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="eedfb-141">011 $1</span><span class="sxs-lookup"><span data-stu-id="eedfb-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="eedfb-142">+441235551010 se torna 011441235551010</span><span class="sxs-lookup"><span data-stu-id="eedfb-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

