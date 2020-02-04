---
title: 'Lync Server 2013: regras de tradução'
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
ms.openlocfilehash: d4ae330633acb04a35abe19356f4b00ff09ef41a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="d2cca-102">Regras de tradução no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2cca-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2cca-103">_**Tópico da última modificação:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d2cca-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d2cca-104">O Lync Server 2013 Enterprise Voice requer que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E. 164 para realizar a pesquisa de número reverso (RNL).</span><span class="sxs-lookup"><span data-stu-id="d2cca-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="d2cca-105">No Microsoft Lync Server 2010, há suporte para as regras de tradução somente para números chamados.</span><span class="sxs-lookup"><span data-stu-id="d2cca-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="d2cca-106">Novo no Microsoft Lync Server 2013, também há suporte para as regras de tradução para números de chamada.</span><span class="sxs-lookup"><span data-stu-id="d2cca-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="d2cca-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span><span class="sxs-lookup"><span data-stu-id="d2cca-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="d2cca-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span><span class="sxs-lookup"><span data-stu-id="d2cca-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="d2cca-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span><span class="sxs-lookup"><span data-stu-id="d2cca-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="d2cca-110">Executando a conversão da rota de saída no servidor, você pode reduzir os requisitos de configuração em cada par de tronco individual para converter os números de telefone em um formato de discagem.</span><span class="sxs-lookup"><span data-stu-id="d2cca-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="d2cca-111">Quando você planeja quais gateways e quantos gateways, associar a um cluster de servidor de mediação específico, pode ser útil agrupar pares de tronco com requisitos de discagem locais semelhantes.</span><span class="sxs-lookup"><span data-stu-id="d2cca-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="d2cca-112">Isso pode reduzir o número de regras de conversão necessárias e o tempo necessário para gravá-las.</span><span class="sxs-lookup"><span data-stu-id="d2cca-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d2cca-113">Associar uma ou mais regras de tradução a uma configuração de tronco do Enterprise Voice deve ser usado como uma alternativa para configurar regras de tradução no par de troncos.</span><span class="sxs-lookup"><span data-stu-id="d2cca-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="d2cca-114">Não associe as regras de tradução a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de tradução no par de tronco, pois as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="d2cca-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="d2cca-115">Exemplo de regras de conversão</span><span class="sxs-lookup"><span data-stu-id="d2cca-115">Example Translation Rules</span></span>

<span data-ttu-id="d2cca-116">Os exemplos a seguir de regras de conversão mostram como você pode desenvolver as regras no servidor para converter números do formato E.164 para um formato local para o par de tronco.</span><span class="sxs-lookup"><span data-stu-id="d2cca-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="d2cca-117">Para obter detalhes sobre como implementar regras de tradução, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="d2cca-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="d2cca-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="d2cca-118">Description</span></span></th>
<th><span data-ttu-id="d2cca-119">Dígitos iniciais</span><span class="sxs-lookup"><span data-stu-id="d2cca-119">Starting Digits</span></span></th>
<th><span data-ttu-id="d2cca-120">Comprimento</span><span class="sxs-lookup"><span data-stu-id="d2cca-120">Length</span></span></th>
<th><span data-ttu-id="d2cca-121">Dígitos a serem removidos</span><span class="sxs-lookup"><span data-stu-id="d2cca-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="d2cca-122">Dígitos a serem adicionados</span><span class="sxs-lookup"><span data-stu-id="d2cca-122">Digits to Add</span></span></th>
<th><span data-ttu-id="d2cca-123">Padrão de correspondência</span><span class="sxs-lookup"><span data-stu-id="d2cca-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="d2cca-124">Tradução</span><span class="sxs-lookup"><span data-stu-id="d2cca-124">Translation</span></span></th>
<th><span data-ttu-id="d2cca-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d2cca-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2cca-126">Discagem convencional de longa distância nos EUA</span><span class="sxs-lookup"><span data-stu-id="d2cca-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="d2cca-127">(retirar o '+')</span><span class="sxs-lookup"><span data-stu-id="d2cca-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="d2cca-128">+1</span><span class="sxs-lookup"><span data-stu-id="d2cca-128">+1</span></span></p></td>
<td><p><span data-ttu-id="d2cca-129">Exatamente 12</span><span class="sxs-lookup"><span data-stu-id="d2cca-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="d2cca-130">1</span><span class="sxs-lookup"><span data-stu-id="d2cca-130">1</span></span></p></td>
<td><p><span data-ttu-id="d2cca-131">0</span><span class="sxs-lookup"><span data-stu-id="d2cca-131">0</span></span></p></td>
<td><p><span data-ttu-id="d2cca-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="d2cca-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="d2cca-133">$1</span><span class="sxs-lookup"><span data-stu-id="d2cca-133">$1</span></span></p></td>
<td><p><span data-ttu-id="d2cca-134">+14255551010 se torna 14255551010</span><span class="sxs-lookup"><span data-stu-id="d2cca-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2cca-135">Discagem de longa distância internacional dos EUA</span><span class="sxs-lookup"><span data-stu-id="d2cca-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="d2cca-136">(retirar '+' e adicionar 011)</span><span class="sxs-lookup"><span data-stu-id="d2cca-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="d2cca-137">Pelo menos 11</span><span class="sxs-lookup"><span data-stu-id="d2cca-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="d2cca-138">1</span><span class="sxs-lookup"><span data-stu-id="d2cca-138">1</span></span></p></td>
<td><p><span data-ttu-id="d2cca-139">011</span><span class="sxs-lookup"><span data-stu-id="d2cca-139">011</span></span></p></td>
<td><p><span data-ttu-id="d2cca-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="d2cca-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="d2cca-141">011$1</span><span class="sxs-lookup"><span data-stu-id="d2cca-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="d2cca-142">+441235551010 se torna 011441235551010</span><span class="sxs-lookup"><span data-stu-id="d2cca-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

