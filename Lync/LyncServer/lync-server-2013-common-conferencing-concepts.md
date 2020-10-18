---
title: 'Lync Server 2013: conceitos comuns de conferência'
description: 'Lync Server 2013: conceitos comuns de conferência.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2eeea52070c65a8a037eb44e75ceb2d937b91a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577007"
---
# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Conceitos comuns de conferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-19_

Alguns conceitos são comuns a todos os tipos de conferências. Eles são descritos nas seções a seguir.

<div>

## <a name="policies-and-bandwidth-management"></a>Políticas e gerenciamento de largura de banda

O Lync Server 2013 permite que os administradores definam políticas para os tipos de reuniões que os usuários podem organizar. Isso ajuda a reforçar as políticas da sua organização e a controlar o uso da largura de banda. Você pode definir uma ampla variedade de políticas de reunião e atribuí-las a usuários individuais e grupos de usuários. Você também pode definir políticas que regem conversas ponto a ponto. Para obter detalhes sobre como definir políticas de conferência, consulte [políticas de conferência no Lync Server 2013](lync-server-2013-conferencing-policies.md) na documentação operações. Para obter detalhes sobre o gerenciamento de largura de banda, consulte [visão geral do controle de admissão de chamada no Lync server 2013](lync-server-2013-overview-of-call-admission-control.md) e [configuração de largura de banda de vídeo no Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

</div>

<div>

## <a name="archiving-and-compliance-features"></a>Recursos de arquivamento e conformidade

O Lync Server 2013 fornece recursos que você pode usar se sua organização deve seguir as regulamentações de conformidade. Você pode usar as habilidades de arquivamento para arquivar o conteúdo apresentado nas reuniões e o conteúdo de conversas de mensagens instantâneas (IM) e de conferências de IM. Para obter detalhes, consulte [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento. Você pode usar recursos de conformidade de Servidor de Chat Persistente para obter conversas com vários participantes, baseadas em tópicos, que são persistentes ao longo do tempo. Para obter detalhes, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento.

</div>

<div>

## <a name="monitoring-feature"></a>Recurso de monitoramento

O recurso Monitoring Server pode capturar registros de detalhes da chamada (CDRs), que você pode usar para rastrear quais usuários falam com quais outros usuários estão usando o Lync Server 2013. Para obter detalhes sobre como implantar e configurar o monitoramento, consulte [Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>Habilitando participação externa em conferências

Você pode aumentar significativamente os benefícios de seu investimento na conferência do Lync Server 2013, permitindo que usuários externos também participem de conferências quando convidados. Os usuários externos podem incluir:

  - **Usuários**     remotos Os próprios usuários da sua organização, quando estão trabalhando fora de seus firewalls e estão usando seus laptops ou outros dispositivos do Lync Server 2013.

  - **Usuários federados**     Usuários de empresas com as quais você trabalha e que também executam o Lync Server 2013. Para permitir que os usuários contatem facilmente esses usuários, você pode criar relacionamentos federados com essas empresas.

  - **Usuários**     anônimos Qualquer outro usuário externo que seja convidado especificamente por seus usuários para participar de conferências específicas. O organizador de uma reunião em sua empresa pode enviar um convite por email de uma conferência para um usuário externo. O email inclui um link no qual o usuário externo pode clicar para ingressar na conferência.

Para habilitar qualquer um ou todos esses cenários, você precisa implantar um servidor de borda para ajudar a habilitar comunicações seguras entre sua implantação do Lync Server 2013 e usuários externos. A solução do Lync Server 2013 usando servidores de borda fornece mídia de alta qualidade do que outras soluções, como uma rede virtual privada (VPN). Para obter detalhes, consulte [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Além disso, independentemente da implantação de Servidores de Borda, você pode permitir que os usuários (isto é, dentro ou fora da organização) disquem de telefones PSTN padrão para participar de conferências de áudio em suas instalações. Isso é feito implantando a conferência discada do Lync Server 2013.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>Compatibilidade entre tipos de reunião e versões de cliente

Se você for ter o Lync Server 2013 interopere com versões anteriores do Office Communications Server e seus clientes, você deve estar ciente dos seguintes problemas:

  - Os usuários que usam o Lync Server 2013 não podem agendar conferências do Live Meeting ou modificar todas as reuniões migradas desse tipo.

  - Os usuários que usam o Lync Server 2013 que precisam participar de conferências do Live Meeting hospedadas em servidores que executam o Office Communications Server 2007 R2 devem ter o cliente do Live Meeting instalado no computador (além do Lync Server 2013) para participar dessas reuniões.

  - Quando conferências do Live Meeting são migradas para o Lync Server 2013, o conteúdo da reunião não migra. Se esse conteúdo for necessário, ele deverá ser carregado novamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

