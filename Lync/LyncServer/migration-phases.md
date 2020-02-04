---
title: Fases de migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76719513d3b9df6b3259efef57fc0bd5ae94050f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>Fases de migração

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-17_

No Lync Server 2013, você define sites em sua rede que contenham componentes do Lync Server 2013. Um site é um conjunto de computadores que são bem conectados por uma rede de alta velocidade e baixa latência, como uma única rede local (LAN) ou duas redes conectadas por uma rede de fibra ótica de alta velocidade.

Um *pool de front-ends* é um conjunto de servidores front-end que são configurados de maneira idêntica e trabalham juntos para fornecer serviços para um grupo comum de usuários. Um pool fornece recursos de escalabilidade e failover para seus usuários. Cada servidor de um pool deve executar funções idênticas de servidor. Um servidor Standard Edition, projetado para pequenas organizações, também define um pool e é executado em um único servidor. Isso permite que você tenha a funcionalidade do Lync Server 2013 para um custo menor, mas não oferece uma solução real de alta disponibilidade.

As fases a seguir descrevem o processo de uma migração de pool do Lync Server 2010 para o Lync Server 2013. Para vários sites que contêm vários pools, cada pool individual deve seguir essa abordagem em fases.

1.  [Fase 1: planejar a migração do Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Fase 2: Preparar para migração](phase-2-prepare-for-migration.md)

3.  [Fase 3: implantar o pool piloto do Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Fase 4: mover os usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Fase 5: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Fase 6: Mover da implantação piloto para produção](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Fase 7: Concluir tarefas pós-migração](phase-7-complete-post-migration-tasks.md)

8.  [Fase 8: Encerrar os pools herdados](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

