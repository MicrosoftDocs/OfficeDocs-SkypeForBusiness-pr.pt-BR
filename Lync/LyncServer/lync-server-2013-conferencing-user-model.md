---
title: Modelo de usuário da conferência do Lync Server 2013
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
ms.openlocfilehash: 4f517e6d3ea3a832c4331377fa49ef7e474377de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>O modelo de usuário de conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Uma parte crítica do modelo de usuário do Lync Server Conferencing é o tamanho da reunião. Após coletar dados de vários pontos de dados (conforme descrito na seção anterior), determinamos o seguinte:

  - A maioria das reuniões é realmente pequena reunião colaborativa com uma média de quatro a seis participantes

  - Aproximadamente 20 a 80% das reuniões têm menos de 20 participantes.

  - 99,98% das reuniões têm menos de 100 participantes.

Além do tamanho da reunião, o modelo de usuário da conferência também leva em conta uma variedade de fatores, como:

  - **Reuniões simultâneas**   quantos usuários devem estar em reuniões ao mesmo tempo?

  - **Media Mix**   quais tipos de mídia estão disponíveis e que devem ser usadas pelos usuários em reuniões?

  - **Os tipos**   de usuário são usuários internos, usuários remotos, usuários federados ou usuários anônimos?

  - **Tempo de aumento da reunião o tempo**   necessário para que todos os usuários de uma reunião ingressem em uma reunião?

Para obter detalhes sobre o modelo de usuário, consulte [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).

Para determinar o número de reuniões e usuários a serem usados para testes, fizemos o seguinte:

  - Retomou o número total de usuários em uma organização (por exemplo, 80.000 usuários) e multiplicado pela taxa de simultaneidade da reunião (por exemplo, 5% de todos os usuários) para determinar o número total de usuários que devem estar em reuniões ao mesmo tempo (neste exemplo , usuários do 4000).

  - Dividiu o número total de usuários pelo número de servidores do Lync Server 2013, front-end na implantação (por exemplo, 8 servidores) para determinar o número estimado de participantes da reunião por servidor front-end (neste exemplo, 500 usuários por servidor front-end).

  - Divida o número de usuários por servidor front-end pelo tamanho médio da reunião (por exemplo, 4 usuários) para determinar o número médio estimado de reuniões por servidor front-end (neste exemplo, reuniões do 125 por servidor front-end).

  - Para obter a carga por mídia em cada servidor front-end, estimamos o mix de mídia. Por exemplo, pressupondo que 75% das reuniões exijam mais do que apenas o suporte a áudio e 50% dessas reuniões exigem compartilhamento de aplicativos, uma média de reuniões do 47 e os usuários da 188 se conectam simultaneamente a cada servidor front-end para compartilhamento de aplicativos.

  - Testou uma variedade de tamanhos de reunião (com base em nosso modelo de usuário de até 250 usuários em um pool compartilhado) para garantir a escalabilidade do servidor.

</div>

<span> </span>

</div>

</div>

</div>

