---
title: Usando o pool estendido de Chat Persistente Chat para recuperação de desastre
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cced4904619fdbda87fecb29f35f11b40270c0ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Usando o pool estendido de Chat Persistente Chat para recuperação de desastre no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

A solução de recuperação de desastres para o servidor de chat persistente baseia-se em um pool de servidores de chat persistentes ampliado. Isso é semelhante à resiliência de site metropolitana no Lync Server 2010; no entanto, não há nenhuma exigência para uma VLAN (rede local virtual) ampliada. Ao esticar um pool de servidores de chat persistente, você essencialmente configura um pool na topologia logicamente, mas coloca fisicamente os servidores no pool em dois data centers diferentes. Configure o espelhamento do SQL Server para o banco de dados da mesma maneira e implante o banco de dados e o espelho no mesmo Data Center. Você deve configurar um banco de dados de backup no data center secundário (com um espelho opcional para fornecer alta disponibilidade durante a recuperação de desastre). Esse é o banco de dados de backup usado para failover durante a recuperação de desastre.

Para obter detalhes sobre como configurar o espelhamento do SQL Server para alta disponibilidade, consulte [espelhamento do SQL Server no Lync Server 2013](lync-server-2013-sql-server-mirroring.md). Para obter detalhes sobre como falhar sobre o banco de dados para recuperação de desastre, consulte Configurando o [envio de log do SQL Server no Lync Server 2013 para o banco de dados do servidor de chat persistente](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) e Configurando o [envio de log do SQL Server entre o espelhamento primário e o log Envio de banco de dados secundário no Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md).

</div>

<span> </span>

</div>

</div>

</div>

