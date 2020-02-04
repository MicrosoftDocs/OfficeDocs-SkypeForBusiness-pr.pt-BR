---
title: 'Lync Server 2013: entroncamento SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76907c1868e9fccb1a31e705c73807a8cbe501b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Entroncamento SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-08-13_

O SIP é usado para iniciar e gerenciar sessões de comunicações de VoIP para o serviço telefônico básico e para vários serviços de comunicação em tempo real adicionais, como sistema de mensagens instantâneas, conferência, detecção de presença e multimídia. Esta seção apresenta informações de planejamento para a implementação de *troncos SIP*, um tipo de conexão SIP que se estende além do limite da rede local.

<div>

## <a name="what-is-sip-trunking"></a>O que é o tronco SIP?

Um tronco SIP é uma conexão do IP estabelece um vínculo de comunicações SIP entre sua organização e um provedor de serviços de telefonia de Internet (ITSP), além do firewall. Normalmente, um tronco SIP é usado para conectar o local central da organização a um ITSP. Em alguns casos, você também pode optar por usar um tronco SIP para conectar a filial a um ITSP.

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>Troncos SIP vs. conexões SIP diretas

O termo *tronco* deriva da tecnologia de circuitos comutados. Ele se refere a uma linha física dedicada que conecta o equipamento de comutação telefônica. Assim como os troncos de TDM, a multiplexação de divisão por tempo (TDM), os troncos SIP são conexões entre duas redes SIP separadas, o Lync Server 2013 Enterprise e o ITSP. Diferentemente dos troncos em circuitos comutados, os troncos SIP são conexões virtuais que podem ser estabelecidas em qualquer tipo de conexão de tronco SIP compatível. Para obter detalhes sobre os tipos de conexão com suporte, consulte [como implementar o entroncamento SIP no Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

As conexões SIP diretas, por outro lado, são conexões SIP que não cruzam o limite de rede local (ou seja, elas se conectam a um gateway PSTN (Rede Telefônica Pública Comutada) ou PBX dentro de sua rede interna). Para obter detalhes sobre como você pode usar as conexões SIP diretas com o Lync Server 2013, consulte [conexões SIP diretas no Lync server 2013](lync-server-2013-direct-sip-connections.md).

</div>

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Visão geral do tronco SIP no Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Como implementar tronco SIP no Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Componentes e topologias para tronco SIP no Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Lista de verificação de tronco SIP para Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

