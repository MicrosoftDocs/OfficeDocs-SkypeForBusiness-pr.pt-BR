---
title: 'Lync Server 2013: Suporte à alta disponibilidade e recuperação de desastre'
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
ms.openlocfilehash: b73f6605f2fff063858a0180d61a306f7dd2d746
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Suporte à alta disponibilidade e recuperação de desastre no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-25_

O Lync Server 2013 fornece alta disponibilidade por redundância de servidor via pool. Se um servidor que executa determinada função falhar, os demais servidores do pool que executam a mesma função assumirão a carga desse servidor. Isso se aplica a Servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores. Para obter detalhes sobre as funções de servidor, consulte [funções de servidor no Lync server 2013](lync-server-2013-server-roles.md).

O Lync Server 2013 também fornece medidas de recuperação de desastres habilitando o emparelhamento de pool. Se implantar essa topologia, você designará pares de pools de Front-Ends, com cada pool de um par localizado em um datacenter e em uma área geográfica distinta. Se um pool ou site ficar inativo, você poderá redirecionar os usuários desse pool para outro pool do par, com o mínimo de interrupção de serviço.

O Lync Server 2013 também oferece suporte à alta disponibilidade do servidor back-end. Esta é uma topologia opcional na qual você implanta dois servidores back-end para um pool de front-end e configura o espelhamento do SQL Server síncrono para todos os bancos de dados do Lync em execução nos servidores back-end.

Para obter detalhes sobre o emparelhamento de pool e o espelhamento do servidor back-end, consulte [planejando alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

<div>

## <a name="see-also"></a>Confira também


[Funções do servidor no Lync Server 2013](lync-server-2013-server-roles.md)  
[Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

