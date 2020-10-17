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
ms.openlocfilehash: 783d2bb8de49fc7660998fcf3cbcb7cdb5c18e8b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530348"
---
# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="4b065-102">Regras de conversão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b065-102">Translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b065-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="4b065-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="4b065-104">Lync Server 2013 Enterprise Voice requer que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E. 164 com o objetivo de executar a pesquisa de número reverso (RNL).</span><span class="sxs-lookup"><span data-stu-id="4b065-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="4b065-105">No Microsoft Lync Server 2010, as regras de conversão têm suporte apenas para números chamados.</span><span class="sxs-lookup"><span data-stu-id="4b065-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="4b065-106">Novo no Microsoft Lync Server 2013, as regras de conversão também têm suporte para números de chamada.</span><span class="sxs-lookup"><span data-stu-id="4b065-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="4b065-107">O *par de tronco* (isto é, o troco de gateway, PBX ou SIP associado) pode exigir que os números estejam no formato de discagem local.</span><span class="sxs-lookup"><span data-stu-id="4b065-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="4b065-108">Para converter os números do formato E.164 em um formato de discagem local, você pode definir uma ou mais regras de conversão para manipular a URI da solicitação antes de roteá-la para o ponto do tronco.</span><span class="sxs-lookup"><span data-stu-id="4b065-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="4b065-109">Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.</span><span class="sxs-lookup"><span data-stu-id="4b065-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="4b065-110">Executando a conversão da rota de saída no servidor, você pode reduzir os requisitos de configuração em cada par de tronco individual para converter os números de telefone em um formato de discagem.</span><span class="sxs-lookup"><span data-stu-id="4b065-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="4b065-111">Quando você planeja quais gateways e quantos gateways estão associados a um cluster do servidor de mediação específico, pode ser útil agrupar os pares de tronco com requisitos de discagem locais semelhantes.</span><span class="sxs-lookup"><span data-stu-id="4b065-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="4b065-112">Isso pode reduzir o número de regras de conversão necessárias e o tempo necessário para gravá-las.</span><span class="sxs-lookup"><span data-stu-id="4b065-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4b065-113">A associação de uma ou mais regras de conversão a uma configuração de tronco do Enterprise Voice deve ser usada como alternativa à configuração de regras de conversão no par de tronco.</span><span class="sxs-lookup"><span data-stu-id="4b065-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="4b065-114">Não associe as regras de conversão a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de conversão no par de tronco, pois as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="4b065-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="4b065-115">Exemplo de regras de conversão</span><span class="sxs-lookup"><span data-stu-id="4b065-115">Example Translation Rules</span></span>

<span data-ttu-id="4b065-116">Os exemplos a seguir de regras de conversão mostram como você pode desenvolver as regras no servidor para converter números do formato E.164 para um formato local para o par de tronco.</span><span class="sxs-lookup"><span data-stu-id="4b065-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="4b065-117">Para obter detalhes sobre como implementar regras de conversão, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="4b065-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="4b065-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="4b065-118">Description</span></span></th>
<th><span data-ttu-id="4b065-119">Dígitos iniciais</span><span class="sxs-lookup"><span data-stu-id="4b065-119">Starting Digits</span></span></th>
<th><span data-ttu-id="4b065-120">Comprimento</span><span class="sxs-lookup"><span data-stu-id="4b065-120">Length</span></span></th>
<th><span data-ttu-id="4b065-121">Dígitos a serem removidos</span><span class="sxs-lookup"><span data-stu-id="4b065-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="4b065-122">Dígitos a serem adicionados</span><span class="sxs-lookup"><span data-stu-id="4b065-122">Digits to Add</span></span></th>
<th><span data-ttu-id="4b065-123">Padrão de correspondência</span><span class="sxs-lookup"><span data-stu-id="4b065-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="4b065-124">Tradução</span><span class="sxs-lookup"><span data-stu-id="4b065-124">Translation</span></span></th>
<th><span data-ttu-id="4b065-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4b065-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b065-126">Discagem convencional de longa distância nos EUA</span><span class="sxs-lookup"><span data-stu-id="4b065-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="4b065-127">(retirar o '+')</span><span class="sxs-lookup"><span data-stu-id="4b065-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="4b065-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="4b065-128">+1</span></span></p></td>
<td><p><span data-ttu-id="4b065-129">Exatamente 12</span><span class="sxs-lookup"><span data-stu-id="4b065-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="4b065-130">1</span><span class="sxs-lookup"><span data-stu-id="4b065-130">1</span></span></p></td>
<td><p><span data-ttu-id="4b065-131">,0</span><span class="sxs-lookup"><span data-stu-id="4b065-131">0</span></span></p></td>
<td><p><span data-ttu-id="4b065-132">^\+(1 \ d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="4b065-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="4b065-133">$1</span><span class="sxs-lookup"><span data-stu-id="4b065-133">$1</span></span></p></td>
<td><p><span data-ttu-id="4b065-134">+14255551010 se torna 14255551010</span><span class="sxs-lookup"><span data-stu-id="4b065-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b065-135">Discagem de longa distância internacional dos EUA</span><span class="sxs-lookup"><span data-stu-id="4b065-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="4b065-136">(retirar '+' e adicionar 011)</span><span class="sxs-lookup"><span data-stu-id="4b065-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="4b065-137">Pelo menos 11</span><span class="sxs-lookup"><span data-stu-id="4b065-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="4b065-138">1</span><span class="sxs-lookup"><span data-stu-id="4b065-138">1</span></span></p></td>
<td><p><span data-ttu-id="4b065-139">00</span><span class="sxs-lookup"><span data-stu-id="4b065-139">011</span></span></p></td>
<td><p><span data-ttu-id="4b065-140">^\+(\d {9} \d +) $</span><span class="sxs-lookup"><span data-stu-id="4b065-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="4b065-141">011 $1</span><span class="sxs-lookup"><span data-stu-id="4b065-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="4b065-142">+441235551010 se torna 011441235551010</span><span class="sxs-lookup"><span data-stu-id="4b065-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

