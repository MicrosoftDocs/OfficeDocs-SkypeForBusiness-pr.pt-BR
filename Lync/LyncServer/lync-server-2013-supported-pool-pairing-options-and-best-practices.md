---
title: Lync Server 2013 opções de emparelhamento de pool compatível e práticas recomendadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c73108f832aaa10b0539aa6fd56b4f4a7bb0cbb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Opções de emparelhamento de pool com suporte e práticas recomendadas para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2017-03-09_

Não há restrições de distância entre dois data centers que incluirão pools de Front End emparelhados entre si. É recomendável usar dois data centers na mesma região geográfica com links de alta velocidade entre eles. É melhor se os dois data centers estiverem suficientemente distantes para evitar que um único desastre atinja ambos ao mesmo tempo.

Ter dois data centers em regiões geográficas distintas é possível, mas poderia incorrer em maior perda de dados devido à latência na replicação dos dados.

Ao planejar quais pools emparelhar, você deve ter em mente que somente os seguintes pares têm suporte:

  - Pools do Enterprise Edition só podem ser emparelhados com outros pools do Enterprise Edition. Da mesma forma, pools do Standard Edition podem ser emparelhados somente com outros pools do Standard Edition.

  - Pools físicos só podem ser emparelhados com outros pools físicos. Da mesma forma, pools virtuais só podem ser emparelhados com outros pools virtuais.

  - Os pools emparelhados devem estar executando o mesmo sistema operacional.

Nem o Construtor de Topologias nem a validação da topologia proibirão o emparelhamento de dois pools de uma forma que estas recomendações não sejam seguidas. Por exemplo, o Construtor de Topologias permite o emparelhamento de um pool do Enterprise Edition com um pool do Standard Edition. No entanto, esses tipos de emparelhamento não são suportados.

Cada pool em um emparelhamento deve ter a capacidade de atender todos os usuários de ambos os pools em caso de desastre.

Se você emparelhar pools do Enterprise Edition, também poderá implementar alta disponibilidade nos servidores de Back End, mas para pares de pools do Standard Edition somente as medidas da recuperação de desastres estão disponíveis.

</div>

<span> </span>

</div>

</div>

</div>

