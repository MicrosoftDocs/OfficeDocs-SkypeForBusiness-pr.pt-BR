---
title: 'Lync Server 2013: planejar a aparência da linha compartilhada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 938bc723d9803acc955899a2b625f983d860b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Planejar a aparência de uma linha compartilhada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-03-21_

Leia este tópico para aprender a planejar a aparência de uma linha compartilhada (SLA) no Lync Server 2013, atualização cumulativa de abril de 2016.

A aparência da linha compartilhada é um recurso do Lync Server 2013, atualização cumulativa de abril de 2016 para manipular várias chamadas em um número específico chamado de número compartilhado. O SLA pode configurar qualquer usuário do Lync habilitado para Enterprise Voice como um número compartilhado com várias linhas para responder a várias chamadas. As chamadas não serão realmente recebidas no número compartilhado, em vez disso, elas serão encaminhadas para os usuários que atuam como representantes para o número compartilhado. Qualquer um dos representantes pode atender a chamada enquanto o restante dos representantes recebe uma notificação no telefone sobre quem obteve o convite e que linha ficou ocupada como resultado. Tanto o número de linhas quanto os representantes são configuráveis para um número compartilhado no SLA. Além disso, as opções avançadas, como BusyOption (o que acontece em uma situação quando todas as linhas estão ocupadas) e MissedCallOption (caso em que nenhum dos representantes atende uma chamada), também podem ser configuradas para um número compartilhado.

O SLA só tem suporte nos seguintes dispositivos telefônicos (não há suporte para clientes do Lync em computadores, telefones celulares ou outros dispositivos):

  - Polycom VVX300 com atualização de firmware 5.4.1

  - Polycom VVX400 com atualização de firmware 5.4.1

  - Polycom VVX500 com atualização de firmware 5.4.1

  - Polycom VVX600 com atualização de firmware 5.4.1

O SLA é um novo recurso do Lync Server 2013, atualização cumulativa de abril de 2016.

Para obter informações sobre a implantação do SLA, consulte [implantar a aparência da linha compartilhada no Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).

<div>

## <a name="feature-list"></a>Lista de recursos

Configuração de um grupo de SLA permite o seguinte:

  - Todos os representantes do grupo podem atender chamadas de entrada para o mesmo número compartilhado. As chamadas podem ser baseadas em PSTN ou em SIP.

  - Os representantes podem reter e atender chamadas.

  - Os representantes podem transferir chamadas para um número externo do grupo SLA.

  - Os representantes podem ver quantas chamadas estão atualmente no número compartilhado e ver o estado de cada uma delas.

  - Você pode configurar um número máximo de chamadas simultâneas para o número compartilhado. Você também pode definir como deseja que as chamadas adicionais sejam manipuladas depois que esse máximo for atingido. As chamadas em excesso podem ser rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou encaminhadas para o correio de voz.

  - Você pode configurar como você deseja que as chamadas não atendidas (chamadas não atendidas após um determinado período de tempo) sejam tratadas. Se você ativar o correio de voz para a identidade do grupo, as chamadas não atendidas automaticamente irão para o correio de voz. Se você não tiver correio de voz habilitado para a identidade do grupo (número compartilhado), você poderá escolher que as chamadas perdidas sejam rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou desconectadas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

