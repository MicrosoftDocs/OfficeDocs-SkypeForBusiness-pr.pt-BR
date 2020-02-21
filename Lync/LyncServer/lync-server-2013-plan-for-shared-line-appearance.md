---
title: 'Lync Server 2013: planejar a aparência da linha compartilhada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6bb768ca892aa684613d1261d88266237ab111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Planejar a aparência de uma linha compartilhada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-03-21_

Leia este tópico para saber como planejar a aparência da linha compartilhada (SLA) no Lync Server 2013, atualização cumulativa de abril de 2016.

A aparência de linha compartilhada é um recurso no Lync Server 2013, atualização cumulativa de abril de 2016 para lidar com várias chamadas em um número específico chamado de número compartilhado. O SLA pode configurar qualquer usuário do Lync habilitado para o Enterprise Voice como um número compartilhado com várias linhas para responder a várias chamadas. As chamadas não são realmente recebidas no número compartilhado, em vez disso são encaminhadas para os usuários que atuam como delegados para o número compartilhado. Qualquer um dos representantes pode pegar a chamada enquanto o restante dos representantes Obtém uma notificação em seu telefone sobre quem selecionou a chamada e qual linha ficou ocupada como resultado. O número de linhas e os representantes são configuráveis para um número compartilhado no SLA. Além disso, as opções avançadas, como BusyOption (o que acontece em uma situação quando todas as linhas estão ocupadas) e MissedCallOption (o caso em que nenhum dos representantes pega uma chamada), também pode ser configurado para um número compartilhado.

Só há suporte para o SLA nos seguintes dispositivos de telefone (não há suporte para clientes do Lync em computadores, telefones celulares ou outros dispositivos):

  - Polycom VVX300 com atualização de firmware 5.4.1

  - Polycom VVX400 com atualização de firmware 5.4.1

  - Polycom VVX500 com atualização de firmware 5.4.1

  - Polycom VVX600 com atualização de firmware 5.4.1

SLA é um novo recurso no Lync Server 2013, atualização cumulativa de abril de 2016.

Para obter informações sobre como implantar o SLA, consulte [implantar aparência de linha compartilhada no Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).

<div>

## <a name="feature-list"></a>Lista de recursos

A configuração de um grupo de SLA permite o seguinte:

  - Todos os representantes no grupo podem responder chamadas de entrada para o mesmo número compartilhado. As chamadas podem ser baseadas em PSTN ou em SIP.

  - Os representantes podem manter e pegar chamadas.

  - Os representantes podem transferir chamadas para um número fora do grupo SLA.

  - Os representantes podem ver quantas chamadas estão no número compartilhado no momento e exibir o status de cada uma dessas chamadas.

  - Você pode configurar um número máximo de chamadas simultâneas para o número compartilhado. Você também pode definir como deseja que as chamadas adicionais sejam tratadas depois que esse máximo for atingido. As chamadas em excesso podem ser rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou encaminhadas para a caixa postal.

  - Você pode configurar como deseja que as chamadas perdidas (chamadas não selecionadas após um determinado tempo) sejam tratadas. Se você habilitar a caixa postal para a identidade do grupo, as chamadas perdidas vão automaticamente para a caixa postal. Se você não tiver a caixa postal habilitada para a identidade do grupo (número compartilhado), você pode escolher para que as chamadas perdidas sejam rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou desconectadas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

