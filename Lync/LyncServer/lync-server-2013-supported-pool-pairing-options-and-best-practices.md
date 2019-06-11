---
title: Opções de emparelhamento de pool compatível com o Lync Server 2013 e práticas recomendadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00202aeb4db74ec81671e557a0679a9f41046b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Opções de emparelhamento de pool compatível e práticas recomendadas para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2017-03-09_

Não há restrição na distância entre dois data centers que incluem pools front-ends emparelhados uns com os outros. Recomendamos que você use dois data centers na mesma região do mundo, com links de alta velocidade entre eles. É melhor se os dois data centers estiverem separados o suficiente para evitar um único desastre ao pressionar ambos ao mesmo tempo.

Ter dois data centers nas regiões do mundo é possível, mas pode causar maior perda de dados devido à latência na replicação de dados.

Ao planejar quais pools emparelhar, você deve ter em mente que somente os emparelhamentos a seguir são aceitos:

  - Os pools Enterprise Edition podem ser emparelhados somente com outros pools Enterprise Edition. Da mesma forma, pools Standard Edition podem ser emparelhados somente com outros pools Standard Edition.

  - Os pools físicos somente podem ser emparelhados com outros pools físicos. Da mesma forma, os pools virtuais somente podem ser emparelhados com outros pools virtuais.

  - Os pools que estão emparelhados em conjunto devem estar executando o mesmo sistema operacional.

Nem o Construtor de Topologias nem a validação da topologia proibirão o emparelhamento de dois pools de uma forma que estas recomendações não sejam seguidas. Por exemplo, o Construtor de Topologias permite o emparelhamento de um pool Enterprise Edition com um pool Standard Edition. No entanto, estes tipos de emparelhamentos não são aceitos.

Cada pool em um par deve ter capacidade para atender todos os usuários de ambos os pools no caso de um desastre.

Se você emparelhar pools da edição Enterprise, também é possível implementar a alta disponibilidade nos servidores back end, mas para pares de pools de edição padrão, somente os indicadores de recuperação de desastres estão disponíveis.

</div>

<span> </span>

</div>

</div>

</div>

