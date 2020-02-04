---
title: 'Lync Server 2013: Failover do repositório do Gerenciamento Central'
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
ms.openlocfilehash: 38bde96b74fa1c00fc937a159c5e8e40df42d4dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a>Failover do repositório do Gerenciamento Central no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

O repositório de gerenciamento central contém dados de configuração sobre servidores e serviços na sua implantação do Lync 2013. Ele fornece um armazenamento robusto e schematized dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Lync 2013. Ele também valida os dados para assegurar a consistência da configuração.

Cada implantação do Lync inclui um repositório central de gerenciamento, que é hospedado pelo servidor back-end de um pool de front-ends.

Quando você estabelece um emparelhamento de pool que inclui o pool que hospeda o repositório de gerenciamento central, um banco de dados de armazenamento central de gerenciamento de backup é configurado no pool de backup e os serviços do repositório de gerenciamento central são instalados nos dois pools. Em qualquer point-in-time, um dos dois bancos de dados do repositório central de gerenciamento é o mestre ativo, e o outro é um standby. O conteúdo é replicado pelo serviço de backup do mestre ativo para o modo de espera.

Durante um failover de pool que envolve os pools que hospedam o repositório de gerenciamento central, o administrador deve fazer failover do repositório de gerenciamento central antes de falhar sobre o pool de front-ends.

Depois que o desastre for resolvido, não será necessário fazer failback do Repositório de Gerenciamento Central. Após o reparo, o repositório de gerenciamento central no pool de backup original pode permanecer como o mestre ativo.

Os destinos projetados para failover do Repositório de Gerenciamento Central para o objetivo de tempo de recuperação (RTO) e para o objetivo de ponto de recuperação (RPO) são de 5 minutos.

</div>

<span> </span>

</div>

</div>

</div>

