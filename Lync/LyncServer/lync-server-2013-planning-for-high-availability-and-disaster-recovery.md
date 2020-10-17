---
title: 'Lync Server 2013: planejamento para alta disponibilidade e recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a44a3b5f83814bf4d4b975dc8f9d548661294e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522108"
---
# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-31_

Como no Lync Server 2010, o principal esquema de alta disponibilidade para a maioria das funções de servidor no Lync Server 2013 é baseado em redundância de servidor por meio de Pooling. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor. Isso se aplica a servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.

O Lync Server 2013 adiciona novas medidas de recuperação de desastres para pools de front-ends, introduzindo dispersão geográficos de seus servidores em dois data centers para fornecer a continuação do serviço, caso um pool ou site inteiro fique inativo.

O Lync Server 2013 também aprimora a alta disponibilidade do servidor back-end, oferecendo suporte ao espelhamento síncrono do SQL para seus bancos de dados back-end.

Essa seção explica como estes principais recursos de alta disponibilidade e de recuperação de disastres, e também cobre quais passos você pode tomar para ter alta disponibilidade e recuperação de disastres também para suas outras funções de servidor.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Recuperação de desastre do pool de front-ends no Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Recuperação de desastre do servidor de borda no Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Planejamento para resiliência do Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Recursos de gerenciamento de chamada para recuperação de desastre no Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Configurando o servidor de chat persistente para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2010 Metropolitan de resiliência de site](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

