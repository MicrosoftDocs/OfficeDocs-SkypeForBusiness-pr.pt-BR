---
title: 'Lync Server 2013: visão geral da implantação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3600df130f0159df0945edb25d72059bb4bcb8a9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522658"
---
# <a name="deployment-overview-for-lync-server-2013"></a>Visão geral da implantação do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-12_

A principal diferença entre o Lync Server 2013 Enterprise Edition e o Lync Server 2013 Standard Edition é que a edição Standard não é compatível com os recursos de alta disponibilidade incluídos na Enterprise Edition. Para alta disponibilidade, você precisa implantar vários servidores front-end em um pool e, em seguida, pode espelhar o servidor que executa o SQL Server. Com o Enterprise Edition, você pode optar por colocar ou definir um servidor de mediação autônomo. O servidor de monitoramento e o servidor de arquivamento podem usar um servidor autônomo executando o SQL Server. Ou podem ter instâncias do SQL Server em execução no servidor de banco de dados para os pools e servidores front-end.

Os servidores que executam o Lync Server 2013 Standard Edition são destinados a organizações menores e locais remotos, que são removidos geograficamente da implantação principal da organização. Dois servidores de servidor Standard Edition emparelhados para failover em caso de desastre podem suportar até 5.000 usuários. Não é possível poolr servidores Standard Edition como servidores de front-end na Enterprise Edition. Além disso, o banco de dados do SQL Server que a Standard Edition usa é um servidor colocado executando o SQL Server Express projetado para lidar com cargas de trabalho do servidor Standard Edition. Isso não significa que todas as funções devem residir em um servidor Standard Edition. Você pode ter servidores de mediação autônomos e servidores de borda. O banco de dados do SQL Server para o repositório de gerenciamento central e para os fins do Lync Server 2013 deve residir no servidor Standard Edition colocado com o servidor que executa o SQL Server. O servidor de monitoramento e o servidor de arquivamento usam um servidor autônomo com o banco de dados do SQL Server.

</div>

<span> </span>

</div>

</div>

</div>

