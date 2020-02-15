---
title: 'Lync Server 2013: planejamento para emparelhamento de pool de front-ends'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4daeb3ea88570afaf9fc90c0e252466be67ed192
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Planejamento para emparelhamento de pool de front-ends no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Para obter os melhores recursos de recuperação de desastre no Lync Server 2013, implante pares de pools de front-ends em dois locais geograficamente dispersos. Cada site contém um pool de Front-End que é emparelhado com um pool de Front-End correspondente em outro local. Ambos os sites estão ativos, e o serviço de backup do Lync Server fornece replicação de dados em tempo real para manter os pools sincronizados. O serviço de backup é um novo recurso no Lync Server 2013, projetado para oferecer suporte à solução de recuperação de desastres. Está instalado em um pool de Front-End ao emparelhar o pool com outro pool de Front-End.

Se o pool em um local falhar, é possível fazer o failover dos usuários deste pool para o pool em outro local, que oferece serviços para todos os usuários em ambos os pools. Para fins de planejamento de capacidade, cada pool deve ser atribuído para lidar com cargas de trabalho de todos os usuários em ambos os pools em caso de desastre.

<div>

## <a name="in-this-section"></a>Nesta Seção

  - [Opções de emparelhamento de pool com suporte e práticas recomendadas para o Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Relações de registradores de backup no Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Tempo de recuperação para failover de pool e failback de pool no Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Failover do repositório de gerenciamento central no Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Segurança de dados de emparelhamento do pool de front-ends no Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

