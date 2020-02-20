---
title: Fases da migração
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
ms.openlocfilehash: e877afc67e5dea1bc2feada22e5bbbbe81e15139
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>Fases da migração

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-17_

No Lync Server 2013, você define sites em sua rede que contenham componentes do Lync Server 2013. Um site é um conjunto de computadores bem conectados por uma rede de baixa latência e alta velocidade, como uma única LAN ou duas redes conectadas por uma rede de fibra óptica de alta velocidade.

Um *Pool de front-end* é um conjunto de servidores de front-end configurados identicamente e que trabalham juntos para oferecer serviços para um grupo de usuários comum. Um pool oferece escalabilidade e capacidade de failover aos seus usuários. Cada servidor em um pool deve executar uma função ou funções do servidor idênticas. Um servidor Standard Edition, projetado para pequenas organizações, também define um pool e é executado em um único servidor. Isso permite que você tenha a funcionalidade do Lync Server 2013 para um custo menor, mas não fornece uma solução de alta disponibilidade real.

As fases a seguir descrevem o processo de migração de pool do Lync Server 2010 para o Lync Server 2013. Para vários sites que contêm pools, cada pool individual deve seguir esta abordagem por fase.

1.  [Fase 1: planejar a migração do Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Fase 2: preparar-se para a migração](phase-2-prepare-for-migration.md)

3.  [Fase 3: implantar o pool piloto do Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Fase 5: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Fase 6: mover da implantação piloto para a produção](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Fase 7: concluir tarefas de migração](phase-7-complete-post-migration-tasks.md)

8.  [Fase 8: encerrar pools herdados](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

