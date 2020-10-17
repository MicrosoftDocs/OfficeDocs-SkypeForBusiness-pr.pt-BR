---
title: Modelo de usuário de conferência do Lync Server 2013
description: Modelo de usuário de conferência do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 699f41303b82f4d8fd2864cbf1b29a1c601b826e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555977"
---
# <a name="the-conferencing-user-model-in-lync-server-2013"></a>O modelo de usuário de conferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Uma parte crítica do modelo de usuário de conferência do Lync Server é o tamanho da reunião. Depois de coletar dados de vários pontos de dados (como descrito na seção anterior), nós determinados o seguinte:

  - A maioria das reuniões é composta por pequenas reuniões colaborativas com uma média de quatro a seis participantes

  - Aproximadamente 80 por cento das reuniões tem menos de 20 participantes.

  - 99,98 por cento das reuniões tem menos de 100 participantes.

Além do tamanho da reunião, o modelo de usuário de conferência também considera vários fatores, como:

  - **Reuniões**     simultâneas Quantos usuários devem estar em reuniões ao mesmo tempo?

  - **Combinação**     de mídia Que tipos de mídia estão disponíveis e que devem ser usados por usuários em reuniões?

  - **Tipos**     de usuário Usuários internos, usuários remotos, usuários federados ou usuários anônimos?

  - Horário de aumento da **reunião**     Quanto tempo leva para que todos os usuários de uma reunião ingressem em uma reunião?

Para obter detalhes sobre o modelo de usuário, consulte [User Models in Lync Server 2013](lync-server-2013-user-models.md).

Para determinar o número de reuniões e usuários para usar em testes foi realizado o seguinte:

  - Pegamos o número total de usuários em uma organização (por exemplo, 80.000 usuários) e multiplicamos pela taxa de simultaneidade da reunião (por exemplo, 5% de todos os usuários) para determinar o número total de usuários esperados em reuniões simultâneas (neste exemplo, 4000 usuários).

  - Dividido o número total de usuários pelo número de servidores front-end do Lync Server 2013 na implantação (por exemplo, 8 servidores) para determinar o número estimado de participantes da reunião por servidor front-end (neste exemplo, 500 usuários por servidor de front-end).

  - Dividido o número de usuários por servidor front-end pelo tamanho médio da reunião (por exemplo, 4 usuários) para determinar o número médio estimado de reuniões por servidor de front-end (neste exemplo, 125 reuniões por servidor de front-end).

  - Para obter a carga por mídia em cada servidor de front-end, estimamos o mix de mídia. Por exemplo, supondo que 75% das reuniões exijam mais do que apenas suporte a áudio e 50% dessas reuniões exigem o compartilhamento de aplicativos, uma média de 47 reuniões e 188 usuários conectam simultaneamente a cada servidor front-end para compartilhamento de aplicativos.

  - Testado em vários tamanhos de reunião (com base em nosso modelo de usuário de até 250 usuários em um pool compartilhado) para garantir a escalabilidade do servidor.

</div>

<span> </span>

</div>

</div>

</div>

