---
title: Fases de migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: No Skype for Business Server 2019, você define sites em sua rede que contenham componentes do Skype for Business Server 2019. Um site é um conjunto de computadores que são bem conectados por uma rede de alta velocidade e baixa latência, como uma única rede local (LAN) ou duas redes conectadas por uma rede de fibra ótica de alta velocidade.
ms.openlocfilehash: 8f50f25536e330a03440702614f81c09ce74518a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298159"
---
# <a name="migration-phases"></a>Fases de migração

No Skype for Business Server 2019, você define sites em sua rede que contenham componentes do Skype for Business Server 2019. Um site é um conjunto de computadores que são bem conectados por uma rede de alta velocidade e baixa latência, como uma única rede local (LAN) ou duas redes conectadas por uma rede de fibra ótica de alta velocidade. 
  
Um pool de front-ends é um conjunto de servidores front-end que são configurados de maneira idêntica e trabalham juntos para fornecer serviços para um grupo comum de usuários. Um pool fornece recursos de escalabilidade e failover para seus usuários. Cada servidor de um pool deve executar funções idênticas de servidor. Um servidor Standard Edition, projetado para pequenas organizações, também define um pool e é executado em um único servidor. Isso permite que você tenha a funcionalidade do Skype for Business Server 2019 para um custo menor, mas não oferece uma solução real de alta disponibilidade. 
  
As fases a seguir descrevem o processo de migração de pool para o Skype for Business Server 2019. Para vários sites que contêm vários pools, cada pool individual deve seguir essa abordagem em fases.
  
1. [Fase 1: Planejar sua migração](phase-1-plan-your-migration.md)
    
2. [Fase 2: Preparar para migração](phase-2-prepare-for-migration.md)
    
3. [Fase 3: implantar o pool piloto do Skype for Business Server 2019](phase-3-deploy-pilot-pool.md)
    
4. [Fase 4: mover os usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Fase 5: Adicionar o servidor de borda do Skype for Business Server 2019 ao pool piloto](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Fase 6: Mover da implantação piloto para produção](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Fase 7: Concluir tarefas pós-migração](phase-7-complete-post-migration-tasks.md)
    
8. [Fase 8: Encerrar os pools herdados](phase-8-decommission-legacy-pools.md)
    

