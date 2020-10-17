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
# <a name="translation-rules-in-lync-server-2013"></a>Regras de conversão no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

Lync Server 2013 Enterprise Voice requer que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E. 164 com o objetivo de executar a pesquisa de número reverso (RNL). No Microsoft Lync Server 2010, as regras de conversão têm suporte apenas para números chamados. Novo no Microsoft Lync Server 2013, as regras de conversão também têm suporte para números de chamada. O *par de tronco* (isto é, o troco de gateway, PBX ou SIP associado) pode exigir que os números estejam no formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir uma ou mais regras de conversão para manipular a URI da solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.

Executando a conversão da rota de saída no servidor, você pode reduzir os requisitos de configuração em cada par de tronco individual para converter os números de telefone em um formato de discagem. Quando você planeja quais gateways e quantos gateways estão associados a um cluster do servidor de mediação específico, pode ser útil agrupar os pares de tronco com requisitos de discagem locais semelhantes. Isso pode reduzir o número de regras de conversão necessárias e o tempo necessário para gravá-las.

<div>


> [!IMPORTANT]  
> A associação de uma ou mais regras de conversão a uma configuração de tronco do Enterprise Voice deve ser usada como alternativa à configuração de regras de conversão no par de tronco. Não associe as regras de conversão a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de conversão no par de tronco, pois as duas regras podem entrar em conflito.



</div>

<div>

## <a name="example-translation-rules"></a>Exemplo de regras de conversão

Os exemplos a seguir de regras de conversão mostram como você pode desenvolver as regras no servidor para converter números do formato E.164 para um formato local para o par de tronco.

Para obter detalhes sobre como implementar regras de conversão, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.


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
<td><p>+ 1</p></td>
<td><p>Exatamente 12</p></td>
<td><p>1</p></td>
<td><p>,0</p></td>
<td><p>^\+(1 \ d {10} ) $</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 se torna 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Discagem de longa distância internacional dos EUA</p>
<p>(retirar '+' e adicionar 011)</p></td>
<td><p>+</p></td>
<td><p>Pelo menos 11</p></td>
<td><p>1</p></td>
<td><p>00</p></td>
<td><p>^\+(\d {9} \d +) $</p></td>
<td><p>011 $1</p></td>
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

