---
title: 'Lync Server 2013: suporte de alta disponibilidade e recuperação de desastre'
description: 'Lync Server 2013: suporte de alta disponibilidade e recuperação de desastre.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8113c6b54cbb55e8149f8d6dd1b53ccbdc9436d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552787"
---
# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Suporte de alta disponibilidade e recuperação de desastre no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-25_

O Lync Server 2013 oferece alta disponibilidade por redundância de servidor por meio de Pooling. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor. Isso se aplica a servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores. Para obter detalhes sobre as funções de servidor, consulte [Server Roles in Lync server 2013](lync-server-2013-server-roles.md).

O Lync Server 2013 também fornece medidas de recuperação de desastres habilitando o emparelhamento do pool. Sr você implantar tal topologia, pode designar pares para pools de Front End, com cada pool em um par localizado em um datacenter separado, e em uma área geográfica separada. Se um pool ou site sair do ar, você pode redirecionar os usuários deste pool para outro pool no par, com o mínimo de interrupção de serviço.

O Lync Server 2013 também oferece suporte à alta disponibilidade do servidor back-end. Esta é uma topologia opcional na qual você implanta dois servidores back-end para um pool de front-ends e configura o espelhamento síncrono do SQL Server para todos os bancos de dados do Lync executados nos servidores back-end.

Para obter detalhes sobre o emparelhamento de pool e o espelhamento de servidor back-end, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

<div>

## <a name="see-also"></a>Confira também


[Funções de servidor no Lync Server 2013](lync-server-2013-server-roles.md)  
[Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

