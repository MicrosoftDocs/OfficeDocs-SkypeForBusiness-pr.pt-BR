---
title: 'Lync Server 2013: como gerenciar grupos de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c0d8ac0fbfa8464fd0cd078fc90784eb9fdd3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a>Gerenciamento de grupos de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2018-02-01_

Grupos de resposta são um recurso de gerenciamento de chamadas que permite que você enfileirar chamadas feitas a uma área específica, como um suporte técnico e, em seguida, encaminhar as chamadas para um grupo designado de pessoas, chamado *agentes*.

Para gerenciar grupos de resposta, você configura grupos de agente, filas e fluxos de trabalho, que definem o que acontece com uma chamada no momento em que ele é colocado até que um agente responda a ele.

<div>


> [!NOTE]  
> Se você tiver mais de 300 fluxos de trabalho em um único pool em sua implantação de grupo de resposta, é melhor usar cmdlets do Shell de gerenciamento do Lync Server para criar os fluxos de trabalho. Se você usar a ferramenta de configuração de grupo de resposta para criar fluxos de trabalho para um pool que tenha mais de 300 fluxos de trabalho, a página da Web levará muito tempo para ser carregada. O número de agentes que estão indiretamente associados a fluxos de trabalho por meio das filas também tem um efeito proporcional na carga da página.



</div>

Os tópicos desta seção fornecem procedimentos passo a passo para tarefas que você pode executar para personalizar e manter o aplicativo de grupo de resposta em sua implantação

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Gerenciamento de grupos de agente de resposta no Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)

  - [Gerenciamento de filas de grupo de resposta no Lync Server 2013](lync-server-2013-managing-response-group-queues.md)

  - [Gerenciamento de fluxos de trabalho de grupo de resposta no Lync Server 2013](lync-server-2013-managing-response-group-workflows.md)

  - [Gerenciando configurações de grupo de resposta no nível do aplicativo no Lync Server 2013](lync-server-2013-managing-application-level-response-group-settings.md)

  - [Movendo grupos de resposta para um novo pool no Lync Server 2013](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [Gerenciando grupos de resposta no Lync Server 2013 durante um desastre](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

