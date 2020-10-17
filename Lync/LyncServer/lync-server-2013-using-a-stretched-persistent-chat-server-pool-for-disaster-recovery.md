---
title: Usando um pool de servidor de chat persistente estendido para recuperação de desastre
description: Usando um pool de servidor de chat persistente estendido para recuperação de desastres.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b83a7226f7b9a49a2676b6222505f53247bd5abf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548537"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Usando um pool de servidor de chat persistente estendido para recuperação de desastre no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

A solução de recuperação de desastre para servidor de chat persistente é criada em um pool de servidor de chat persistente estendido. Isso é semelhante à resiliência de site metropolitana no Lync Server 2010; no entanto, não há nenhum requisito para uma VLAN (rede local virtual) estendida. Ao alongar o pool de servidor de chat persistente, você essencialmente configura um pool na topologia logicamente, mas coloca fisicamente os servidores no pool em dois data centers diferentes. Configure o espelhamento do SQL Server para o banco de dados da mesma maneira e implante o banco de dados e o espelho no mesmo Data Center. Você deve configurar um banco de dados de backup no data center secundário (com um espelho opcional para fornecer alta disponibilidade durante a recuperação de desastres). Ele é o banco de dados de backup usado para failover durante a recuperação de desastres.

Para obter detalhes sobre como configurar o espelhamento do SQL Server para alta disponibilidade, consulte [espelhamento do SQL Server no Lync Server 2013](lync-server-2013-sql-server-mirroring.md). Para obter detalhes sobre como fazer o failover do banco de dados para recuperação de desastre, consulte [Configuring SQL Server log Shipping in Lync server 2013 for persistent chat Server-Primary Database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) e [setting up SQL Server log Shipping entre o espelho primário e o banco de dados secundário de envio de logs no Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).

</div>

<span> </span>

</div>

</div>

</div>

