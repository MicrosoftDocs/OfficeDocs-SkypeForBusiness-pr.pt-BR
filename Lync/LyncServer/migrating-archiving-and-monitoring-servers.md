---
title: Migrar servidores de Arquivamento e de Monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572cbee046ed960017a3b60b7ae68c58ec67cf23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migrar servidores de Arquivamento e de Monitoramento

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

Se você implantou o servidor de arquivamento e monitorando o servidor em seu ambiente do Lync Server 2010, poderá implantar esses servidores no ambiente do Lync Server 2013 após migrar seus pools front-ends. No entanto, se a funcionalidade de arquivamento e monitoramento for essencial para a sua organização, você deverá adicionar arquivamento e monitoramento ao pool piloto do Lync Server 2013 antes de migrar para que a funcionalidade esteja disponível durante o processo de migração.

Se você quiser a funcionalidade de arquivamento e monitoramento durante o processo de migração, tenha em mente as seguintes considerações:

  - O arquivamento de dados e monitoramento de dados não são movidos para a implantação do Lync Server 2013. Os dados que você deve fazer backup antes de descomissionar o ambiente herdado serão o seu histórico de atividades no ambiente do Lync Server 2010.

  - A versão do Lync Server 2010 do servidor de arquivamento e o Monitoring Server podem ser associadas apenas a um pool de front-end do Lync Server 2010. No Lync Server 2013, o arquivamento e o monitoramento não são mais funções do servidor, mas serviços integrados ao pool de front-ends do Lync Server 2013.

  - Durante o tempo em que suas implantações do Lync Server e do Lync Server 2013 coexistem, a versão do Lync Server 2010 do servidor de arquivamento e o Monitoring Server coletam dados para os usuários hospedados nos pools do Lync Server 2010. O arquivamento e o monitoramento no Lync Server 2013 coletam dados para usuários hospedados no Lync Server 2013 pools.
    
    <div>
    

    > [!NOTE]  
    > Durante a fase de migração quando você ainda estiver usando o servidor de borda herdado com o novo pool piloto do Lync Server 2013, a versão do servidor de arquivamento do Lync Server 2010 continua a coletar dados para os usuários hospedados no Lync Server 2010 pools e o arquivamento no Lync Server 2013 reúne dados para os usuários hospedados nos pools do Lync Server 2013.

    
    </div>

  - Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com o arquivamento e o monitoramento no Lync Server 2013, consulte o fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

