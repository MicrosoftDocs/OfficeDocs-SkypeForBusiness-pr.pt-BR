---
title: Migrar servidores de Arquivamento e de Monitoramento
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
ms.openlocfilehash: ee3abd26386ad26e3b6628d5b9db873bd17373be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743771"
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

Se você implantou o servidor de arquivamento e monitorando o servidor no Office Communications Server 2007 R2, poderá implantar esses servidores no ambiente do Lync Server 2013 depois de migrar seus pools front-ends. No entanto, se a funcionalidade de arquivamento e monitoramento for essencial para sua organização, você deverá adicionar arquivamento e monitoramento ao pool piloto antes de migrar para que a funcionalidade esteja disponível durante o processo de migração.

Se você quiser a funcionalidade de arquivamento e monitoramento durante a fase de migração e de coexistência, tenha em mente as seguintes considerações:

  - O arquivamento de dados e monitoramento de dados não são movidos para a implantação do Lync Server 2013. Os dados que você reproduzem antes de descomissionar o ambiente herdado serão seu histórico de atividades no Office Communications Server 2007 R2.

  - A versão do Office Communications Server 2007 R2 do servidor de arquivamento e Monitoring Server somente pode ser associada a um pool de front-end do Office Communications Server 2007 R2. No Lync Server 2013, o arquivamento e o monitoramento não são mais funções do servidor, mas serviços integrados ao pool de front-ends do Lync Server 2013.

  - Durante o tempo em que suas implantações do Lync Server e do Lync Server 2013 coexistem, a versão do Office Communications Server 2007 R2 do servidor de arquivamento e o Monitoring Server reúne dados para os usuários hospedados no Office Communications Server 2007 R2 pools. A versão do Lync Server 2013 do servidor de arquivamento e o Monitoring Server coletam dados para os usuários hospedados no Lync Server 2013 pools.
    
    <div>
    

    > [!NOTE]  
    > Durante a fase de migração, quando você ainda estiver usando seu servidor de borda herdado com o novo pool piloto do Lync Server 2013, a versão do Office Communications Server 2007 R2 do servidor de arquivamento continua a coletar dados para os usuários hospedados no Office Communications Server 2007 Os pools R2 e a versão do Lync Server 2013 do servidor de arquivamento coletam dados para os usuários hospedados no Lync Server 2013 pools.

    
    </div>

  - Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com o servidor de arquivamento e monitoração do servidor, fale com o fornecedor sobre quando e como você precisa integrar a solução de terceiros ao Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

