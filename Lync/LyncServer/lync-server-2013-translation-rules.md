---
title: 'Lync Server 2013: regras de tradução'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Regras de tradução no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

O Lync Server 2013 Enterprise Voice requer que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E. 164 para realizar a pesquisa de número reverso (RNL). No Microsoft Lync Server 2010, há suporte para as regras de tradução somente para números chamados. Novo no Microsoft Lync Server 2013, também há suporte para as regras de tradução para números de chamada. The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format. To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer. For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.

Executando a conversão da rota de saída no servidor, você pode reduzir os requisitos de configuração em cada par de tronco individual para converter os números de telefone em um formato de discagem. Quando você planeja quais gateways e quantos gateways, associar a um cluster de servidor de mediação específico, pode ser útil agrupar pares de tronco com requisitos de discagem locais semelhantes. Isso pode reduzir o número de regras de conversão necessárias e o tempo necessário para gravá-las.

<div>


> [!IMPORTANT]  
> Associar uma ou mais regras de tradução a uma configuração de tronco do Enterprise Voice deve ser usado como uma alternativa para configurar regras de tradução no par de troncos. Não associe as regras de tradução a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de tradução no par de tronco, pois as duas regras podem entrar em conflito.



</div>

<div>

## <a name="example-translation-rules"></a>Exemplo de regras de conversão

Os exemplos a seguir de regras de conversão mostram como você pode desenvolver as regras no servidor para converter números do formato E.164 para um formato local para o par de tronco.

Para obter detalhes sobre como implementar regras de tradução, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.


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
<th>Descrição</th>
<th>Dígitos iniciais</th>
<th>Comprimento</th>
<th>Dígitos a serem removidos</th>
<th>Dígitos a serem adicionados</th>
<th>Padrão de correspondência</th>
<th>Tradução</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Discagem convencional de longa distância nos EUA</p>
<p>(retirar o '+')</p></td>
<td><p>+1</p></td>
<td><p>Exatamente 12</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1 \ d{10}) $</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 se torna 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Discagem de longa distância internacional dos EUA</p>
<p>(retirar '+' e adicionar 011)</p></td>
<td><p>+</p></td>
<td><p>Pelo menos 11</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011$1</p></td>
<td><p>+441235551010 se torna 011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

