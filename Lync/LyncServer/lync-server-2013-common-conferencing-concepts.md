---
title: 'Lync Server 2013: conceitos comuns de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 240415ccdf8c0ab9be2eaf10304973b62c302c79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Conceitos comuns de conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-19_

Vários conceitos são comuns a todos os tipos de conferências. Elas são descritas nas seções a seguir.

<div>

## <a name="policies-and-bandwidth-management"></a>Gerenciamento de políticas e largura de banda

O Lync Server 2013 permite que os administradores definam políticas para os tipos de reuniões que os usuários podem organizar. Isso ajuda você a impor as políticas da sua organização e controlar o uso da largura de banda. Você pode definir uma grande variedade de políticas de reunião e atribuí-las a usuários individuais e grupos de usuários. Você também pode definir políticas que regem as conversas ponto a ponto. Para obter detalhes sobre como definir políticas de conferência, consulte [políticas de conferência no Lync Server 2013](lync-server-2013-conferencing-policies.md) na documentação de operações. Para obter detalhes sobre o gerenciamento de largura de banda, consulte [visão geral do controle de admissão de chamadas no Lync server 2013](lync-server-2013-overview-of-call-admission-control.md) e [configuração da largura de banda do vídeo no Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

</div>

<div>

## <a name="archiving-and-compliance-features"></a>Recursos de arquivamento e conformidade

O Lync Server 2013 fornece recursos que você pode usar se a sua organização deve seguir as normas de conformidade. Você pode usar os recursos de arquivamento para arquivar conteúdo apresentado em reuniões e também o conteúdo de conversas de mensagens instantâneas (IM) e conferências de mensagens instantâneas. Para obter detalhes, consulte [planejando o arquivamento no Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento. Você pode usar os recursos de conformidade do servidor de chat persistente para arquivar conversas com base em tópicos de vários participantes que persistem ao longo do tempo. Para obter detalhes, consulte [planejando o servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento.

</div>

<div>

## <a name="monitoring-feature"></a>Recurso de monitoramento

O recurso Monitoring Server pode capturar registros de detalhes de chamadas (CDRs), que você pode usar para acompanhar quais usuários falam com quais outros usuários que usam o Lync Server 2013. Para obter detalhes sobre como implantar e configurar o monitoramento, consulte Implantando o [monitoramento no Lync Server 2013](lync-server-2013-deploying-monitoring.md).

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>Como habilitar a participação externa em conferências

Você pode aumentar bastante as vantagens do seu investimento na conferência do Lync Server 2013, permitindo que usuários externos também participem de conferências quando convidados. Entre os usuários externos podem estar:

  - **Usuários remotos**   os próprios usuários da organização, quando estiverem trabalhando fora dos firewalls e estiverem usando seus laptops ou outros dispositivos do Lync Server 2013.

  - **Usuários federados usuários**   de empresas com quem você trabalha com quem também executam o Lync Server 2013. Para habilitar que seus usuários entrem em contato facilmente com esses usuários, crie relacionamentos federados com essas empresas.

  - **Usuários anônimos**   quaisquer outros usuários externos convidados especificamente para que os usuários ingressem em conferências específicas. O organizador de uma reunião em sua empresa pode enviar um convite de uma conferência por email a um usuário externo. O email inclui um link no qual o usuário externo pode clicar para ingressar na conferência.

Para habilitar qualquer um desses cenários, você precisa implantar um servidor de borda para ajudar a habilitar comunicações seguras entre a implantação do Lync Server 2013 e os usuários externos. A solução do Lync Server 2013 usando servidores de borda fornece mídia de alta qualidade do que outras soluções, como uma rede virtual privada (VPN). Para obter detalhes, consulte [planejando o acesso de usuários externos no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Além disso, se você implantou ou não servidores de borda, pode habilitar usuários (ou seja, dentro ou fora da sua organização) para discar de telefones PSTN padrão para ingressar em conferências de áudio locais. Isso é realizado implantando a conferência discada do Lync Server 2013.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>Compatibilidade entre tipos de reunião e versões de cliente

Se você pretende que o Lync Server 2013 interopere com versões anteriores do Office Communications Server e seus clientes, você deve estar ciente dos seguintes problemas:

  - Os usuários que usam o Lync Server 2013 não podem agendar conferências de reunião ao vivo ou modificar qualquer reunião migrada desse tipo.

  - Os usuários que usam o Lync Server 2013 que precisam participar de conferências de reuniões ao vivo hospedadas em servidores que executam o Office Communications Server 2007 R2 devem ter o cliente Live Meeting instalado no computador (além do Lync Server 2013) para participar dessas reuniões.

  - Quando conferências de reuniões ao vivo são migradas para o Lync Server 2013, o conteúdo da reunião não é migrado. Se esse conteúdo for necessário, ele deverá ser carregado novamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

