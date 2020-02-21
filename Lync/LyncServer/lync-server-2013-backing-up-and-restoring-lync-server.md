---
title: 'Lync Server 2013: fazendo backup e restaurando o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00f2f907c8efb663816ca50152643cea70fcc2ff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Fazendo backup e restaurando o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Nesta seção, você encontrará as práticas recomendadas para fazer backup dos dados do Lync Server 2013 e para restaurá-lo se você tiver uma falha. Essas práticas recomendadas aplicam-se às seguintes situações:

  - Um pool completo do Lync Server de qualquer tipo (servidor front-end, servidor de borda, servidor de mediação, servidor de chat persistente ou diretor) ou um servidor individual em um desses pools.

  - O servidor de gerenciamento central

  - Um servidor Standard Edition

  - Um servidor back-end Enterprise Edition

  - Um repositório de arquivos

  - Banco de dados de arquivamento, banco de dados de monitoramento ou banco de dados de chat persistente

Esta seção não inclui informações sobre a restauração de um site inteiro ou para o desenvolvimento de um site em espera. Para obter detalhes sobre o desenvolvimento de uma solução de recuperação de desastres com pools de front-ends emparelhados, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Este é o método recomendado para o planejamento da recuperação de desastres.

Se você tiver implantado pools de front-ends emparelhados, se um desses pools falhar e tornar-se irrecuperável, você poderá restaurar esse pool com um novo FQDN (nome de domínio totalmente qualificado) de seu pool emparelhado. Para obter detalhes sobre as etapas para realizar essa recuperação, consulte [failover de um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Além disso, se você quiser recriar um pool com falha e irrecuperável que faz parte de um par de front-ends, poderá usar as etapas de [execução de um failover de pool de front-ends ABC no Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

O método descrito neste documento envolve considerações especiais durante a fase de planejamento. Para obter detalhes, consulte [estabelecendo um plano de backup e restauração para o Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Preparando para backup e restauração do Lync Server 2013](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Fazendo backup de dados e configurações no Lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Restaurando dados e configurações no Lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

