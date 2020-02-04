---
title: 'Lync Server 2013: Planejamento para emparelhamento de pool Front-End'
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
ms.openlocfilehash: d85f6e19f3aa74c09a522e737d1223095f17d7c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Planejamento para emparelhamento de pool Front-End no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Para obter os melhores recursos de recuperação de desastre no Lync Server 2013, implante pares de pools front-end em dois locais geograficamente dispersos. Cada site contém um pool de front-ends que está emparelhado com um pool de front-end correspondente no outro site. Os dois sites estão ativos e o serviço de backup do Lync Server fornece replicação de dados em tempo real para manter os pools sincronizados. O serviço de backup é um novo recurso do Lync Server 2013, projetado para dar suporte à solução de recuperação de desastres. Ele é instalado em um pool de front-ends quando você emparelha o pool com outro pool de front-end.

Se o pool em um site falhar, você poderá fazer failover dos usuários desse pool para o pool no outro site, que fornece serviços a todos os usuários em ambos os pools. Para fins de planejamento da capacidade, cada pool deve ser projetado para lidar com as cargas de trabalho de todos os usuários em ambos os pools, no caso de um desastre.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Opções de emparelhamento de pool compatível e práticas recomendadas para o Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Relacionamentos de Registradores de backup no Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Tempo de recuperação para failover e failback de pool no Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Failover do repositório do Gerenciamento Central no Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Segurança de dados de emparelhamento do pool Front End no Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

