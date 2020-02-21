---
title: Migrando servidores de arquivamento e monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67896576fce21eea630533a5826bbcbc53392fa0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migrando servidores de arquivamento e monitoramento

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Se você implantou o servidor de arquivamento e o Monitoring Server no Office Communications Server 2007 R2, pode implantar esses servidores em seu ambiente do Lync Server 2013 após migrar seus pools de front-end. Se as funcionalidades de arquivamento e monitoração forem cruciais para a organização, no entanto, você deverá adicionar o Arquivamento e Monitoramento ao pool piloto antes de migrar, de forma que a funcionalidade fique disponível durante o processo de migração.

Se você deseja as funcionalidades de arquivamento e monitoração durante a migração e a fase de coexistência, lembre-se das considerações a seguir:

  - Os dados de arquivamento e de monitoramento não são movidos para a implantação do Lync Server 2013. Os dados que você fez backup antes de encerrar o ambiente herdado serão seu histórico de atividades no Office Communications Server 2007 R2.

  - A versão do Office Communications Server 2007 R2 do servidor de arquivamento e o Monitoring Server só podem ser associadas a um pool de front-ends do Office Communications Server 2007 R2. No Lync Server 2013, o arquivamento e o monitoramento não são mais funções de servidor, mas os serviços integrados ao pool de front-ends do Lync Server 2013.

  - Durante o tempo em que suas implantações herdadas do Lync Server 2013 coexistem, a versão do Office Communications Server 2007 R2 do servidor de arquivamento e o Monitoring Server reúnem dados para usuários hospedados em pools do Office Communications Server 2007 R2. A versão do Lync Server 2013 do servidor de arquivamento e o Monitoring Server reúnem dados para usuários hospedados no Lync Server 2013 pools.
    
    <div>
    

    > [!NOTE]  
    > Durante a fase de migração quando você ainda estiver usando seu servidor de borda herdado com o novo pool piloto do Lync Server 2013, a versão do Office Communications Server 2007 R2 do servidor de arquivamento continua a coletar dados para usuários hospedados no Office Communications Server 2007 Os pools R2 e a versão do Lync Server 2013 do servidor de arquivamento coleta dados para usuários hospedados no Lync Server 2013 pools.

    
    </div>

  - Se você usar uma solução de arquivamento e monitoramento de terceiros junto com o servidor de arquivamento e o servidor de monitoramento, converse com seu fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

