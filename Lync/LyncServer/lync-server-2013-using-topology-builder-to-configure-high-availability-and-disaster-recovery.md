---
title: Usando o Construtor de Topologia para configurar alta disponibilidade e recuperação de desastre
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b167ea64f42510febe0f405d15e2eafab7efc2bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Usando o Construtor de Topologia para configurar alta disponibilidade e recuperação de desastre no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

Execute as etapas a seguir no construtor de topologias para configurar a alta disponibilidade e a recuperação de desastres para o servidor de chat persistente.

1.  Adicione os bancos de dados espelho e os repositórios secundários do banco de dados do SQL Server de envio de log.

2.  Edite as propriedades do serviço do servidor de chat persistente para:
    
    1.  Ativar o espelhamento do banco de dados primário.
    
    2.  Adicione a loja principal do SQL Server do espelho.
    
    3.  Habilite o banco de dados de envio de log do SQL Server.
    
    4.  Adicione o repositório do SQL Server secundário de envio de logs do SQL Server.
    
    5.  Adicione o espelho do SQL Server Store para o banco de dados secundário.
    
    6.  Publique a topologia.

</div>

<span> </span>

</div>

</div>

</div>

