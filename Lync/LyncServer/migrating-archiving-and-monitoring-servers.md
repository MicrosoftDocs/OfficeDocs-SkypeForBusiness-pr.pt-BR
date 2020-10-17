---
title: Migrar servidores de Arquivamento e de Monitoramento
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba32bf2b35a0d2e8b0048ebb9c62aac09cb6eb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527404"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrar servidores de Arquivamento e de Monitoramento

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Se você implantou o servidor de arquivamento e o Monitoring Server no seu ambiente do Lync Server 2010, pode implantar esses servidores no seu ambiente do Lync Server 2013 após migrar seus pools de front-end. No entanto, se a funcionalidade de arquivamento e monitoramento for crítica para sua organização, você deverá adicionar arquivamento e monitoramento ao pool piloto do Lync Server 2013 antes de migrar para que a funcionalidade esteja disponível durante o processo de migração.

Se você deseja as funcionalidades de arquivamento e monitoração durante o processo de migração, lembre das considerações a seguir:

  - Os dados de arquivamento e de monitoramento não são movidos para a implantação do Lync Server 2013. Os dados submetidos ao backup antes de desprogramar o ambiente de legado serão seu histórico da atividade no ambiente do Lync Server 2010.

  - A versão do Lync Server 2010 do servidor de arquivamento e o Monitoring Server só podem ser associadas a um pool de front-ends do Lync Server 2010. No Lync Server 2013, o arquivamento e o monitoramento não são mais funções de servidor, mas os serviços integrados ao pool de front-ends do Lync Server 2013.

  - Durante o tempo em que suas implantações herdadas do Lync Server 2013 coexistem, a versão do Lync Server 2010 do servidor de arquivamento e o Monitoring Server reúnem dados para usuários hospedados no Lync Server 2010 pools. Arquivamento e monitoramento no Lync Server 2013 coletar dados para usuários hospedados no Lync Server 2013 pools.
    
    <div>
    

    > [!NOTE]  
    > Durante a fase de migração quando você ainda estiver usando seu servidor de borda herdado com o novo pool piloto do Lync Server 2013, a versão do servidor de arquivamento do Lync Server 2010 continua a coletar dados para usuários hospedados no Lync Server 2010 pools e o arquivamento no Lync Server 2013 coleta dados para usuários hospedados em pools do Lync Server 2013.

    
    </div>

  - Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com arquivamento e monitoramento no Lync Server 2013, consulte seu fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

