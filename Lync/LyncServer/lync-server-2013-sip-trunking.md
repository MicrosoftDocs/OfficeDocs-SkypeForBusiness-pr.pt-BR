---
title: 'Lync Server 2013: tronco SIP'
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
ms.openlocfilehash: fe2ea13628e9a4ede3daa2b14ebbb3941ce30aa1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-08-13_

O SIP é usado para iniciar e gerenciar sessões de comunicações de VoIP (voz sobre IP) para o serviço telefônico básico e para vários serviços de comunicação em tempo real adicionais, como serviços de mensagens instantâneas, conferência, detecção de presença e multimídia. Esta seção oferece informações de planejamento para a implementação de *troncos SIP*, um tipo de conexão SIP que se estende além do limite da rede local.

<div>

## <a name="what-is-sip-trunking"></a>O que é o tronco SIP?

Um tronco SIP é uma conexão do IP estabelece um vínculo de comunicações SIP entre sua organização e um provedor de serviços de telefonia de Internet (ITSP), além do firewall. Normalmente, um tronco SIP é usado para conectar o site central da organização a um ITSP. Em alguns casos, você também pode optar por usar um tronco SIP para conectar o site da filial a um ITSP.

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>Troncos SIP vs. Conexões diretas do cabo SIP

O termo *tronco * deriva da tecnologia de comutação de circuitos. Refere-se a uma linha física dedicada que conecta o equipamento de comutação telefônica. Assim como seus troncos do predecessor, a multiplexação de divisão de tempo (TDM), os troncos SIP são conexões entre duas redes SIP separadas, o Lync Server 2013 Enterprise e o ITSP. Diferentemente dos troncos de comutação de circuitos, os troncos SIP são conexões virtuais que podem ser estabelecidas sobre qualquer tipo de conexão de troncos SIP compatíveis. Para obter detalhes sobre os tipos de conexão suportados, consulte [como implementar o tronco SIP no Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

As conexões SIP diretas, por outro lado, são conexões de SIP que não atravessam o limite de rede local (ou seja, elas se conectam a um gateway PSTN ou PBX dentro de sua rede interna). Para obter detalhes sobre como você pode usar as conexões SIP diretas com o Lync Server 2013, consulte [Direct SIP Connections in Lync server 2013](lync-server-2013-direct-sip-connections.md).

</div>

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Visão geral do tronco SIP no Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Como faço para implementar o tronco SIP no Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Componentes e topologias para tronco SIP no Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Tronco SIP do site de filial no Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Lista de verificação de implantação de tronco SIP para Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

