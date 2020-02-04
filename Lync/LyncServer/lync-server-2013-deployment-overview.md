---
title: 'Lync Server 2013: Visão geral de implantação'
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
ms.openlocfilehash: 3d237e0ba3f94f81ce3988e2ce8994d49f97087d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Visão geral de implantação para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-12_

A principal diferença entre o Lync Server 2013 Enterprise Edition e o Lync Server 2013 Standard Edition é que a edição padrão não é compatível com os recursos de alta disponibilidade incluídos na Enterprise Edition. Para alta disponibilidade, você precisa implantar vários servidores front-end em um pool e, em seguida, pode espelhar o servidor que executa o SQL Server. Com a Enterprise Edition, você pode optar por posicionar ou definir um servidor autônomo de mediação. O servidor de monitoramento e o servidor de arquivamento podem usar um servidor autônomo que executa o SQL Server. Ou podem ter instâncias do SQL Server em execução no servidor de banco de dados para os servidores e pools de front-end.

Os servidores que executam o Lync Server 2013 Standard Edition são destinados a organizações menores e locais remotos, que são geograficamente removidos da implantação principal da organização. Dois servidores de servidor Standard Edition emparelhados juntos para failover em caso de desastre podem oferecer suporte a até 5.000 usuários. Você não pode pools de servidores padrão da edição, como os servidores front-end na Enterprise Edition. Além disso, o banco de dados SQL Server que a edição padrão usa é um servidor posicionado que executa o SQL Server Express projetado para manipular as cargas de trabalho padrão do servidor da edição. Isso não significa que todas as funções devem residir em um servidor Standard Edition. Você pode ter servidores de mediação autônomos e servidores de borda. O banco de dados do SQL Server para o repositório de gerenciamento central e para os fins do Lync Server 2013 deve residir no servidor Standard Edition posicionado com o servidor que executa o SQL Server. O servidor de monitoramento e o servidor de arquivamento usam um servidor autônomo com o banco de dados do SQL Server.

</div>

<span> </span>

</div>

</div>

</div>

