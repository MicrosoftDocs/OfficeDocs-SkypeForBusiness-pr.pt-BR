---
title: Lync Server 2013 failover do repositório de gerenciamento central
description: Lync Server 2013 failover do repositório de gerenciamento central.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2960a55d6bdc49e00bf22997bc53946d4770fde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544367"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a>Failover do repositório de gerenciamento central no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

O repositório de gerenciamento central contém dados de configuração sobre servidores e serviços em sua implantação do Lync 2013. Ele fornece um armazenamento robusto, esquematizado dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Lync 2013. Também valida os dados para garantir a consistência da configuração.

Cada implantação do Lync inclui um repositório de gerenciamento central, que é hospedado pelo servidor back-end de um pool de front-ends.

Quando você estabelece um emparelhamento de pool que inclui o pool que hospeda o repositório de gerenciamento central, um banco de dados do repositório de gerenciamento central de backup é configurado no pool de backup e os serviços do repositório de gerenciamento central estão instalados nos dois pools. A qualquer momento, um dos dois bancos de dados do repositório de gerenciamento central é o mestre ativo e o outro é um standby. O conteúdo é replicado pelo Serviço de Backup do mestre ativo para o em espera.

Durante um failover de pool que envolve os pools que hospedam o repositório de gerenciamento central, o administrador deve fazer failover do repositório de gerenciamento central antes de falhar sobre o pool de front-ends.

Após o desastre ser reparado, não é necessário fazer failback do repositório de gerenciamento central. Após o reparo, o repositório de gerenciamento central no pool de backup original pode permanecer como o mestre ativo.

Os destinos de engenharia para failover do repositório de gerenciamento central são 5 minutos para o objetivo de tempo de recuperação (RTO) e 5 minutos para o objetivo de ponto de recuperação (RPO).

</div>

<span> </span>

</div>

</div>

</div>

