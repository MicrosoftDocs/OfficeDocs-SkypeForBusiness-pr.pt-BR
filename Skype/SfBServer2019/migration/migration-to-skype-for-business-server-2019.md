---
title: Migração para o Skype for Business Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Os tópicos desta seção guiam você pelo processo de migração para o Skype for Business Server 2019.
ms.openlocfilehash: bd1513e5ca2a33449f982394e4abc15b9616393b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298145"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migração para o Skype for Business Server 2019

Os tópicos desta seção guiam você pelo processo de migração para o Skype for Business Server 2019. Este artigo aborda a migração do Lync Server 2013 ou do Skype for Business Server 2015 para o Skype for Business Server 2019.

> [!IMPORTANT]
> Ao longo do conteúdo, usamos o termo *herdado* para consultar o Lync Server 2013 ou o Skype for Business Server herdado 2015 que você está migrando para o Skype for business Server 2019.
  
> [!IMPORTANT]
> Este guia descreve as etapas geralmente necessárias para realizar cada fase da migração. Ele não trata cada possível topologia de implantação herdada ou todos os possíveis cenários de migração. Portanto, talvez você não precise executar todas as etapas descritas ou talvez seja necessário executar etapas adicionais, dependendo da sua implantação. Este guia também fornece exemplos de etapas de verificação. Estas etapas de verificação são fornecidas para ajudá-lo a entender o que você precisa procurar para garantir que cada fase seja concluída com êxito enquanto avança pela migração. Personalize essas etapas de verificação para seu processo de migração específico. 
  
Este guia fornece informações específicas para atualizar sua implantação existente. Ele não explica como alterar a topologia existente. Este guia não aborda a implementação de novos recursos. Quando um procedimento detalhado é documentado em outro lugar, este guia direciona você para o artigo ou para a seção do artigo. 
  
Este artigo define termos conforme especificado na lista a seguir.
  
**migração:** Mover a implantação de produção do Lync Server 2013 ou do Skype for Business Server 2015 para o Skype for Business Server 2019.
    
**coexistência:** O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Skype for Business Server 2019 e outras funcionalidades ainda permanecem em uma versão anterior.
    
**interoperabilidade:** A capacidade de sua implantação operar com sucesso durante o período de coexistência.

**herdado:** O sistema do qual você está migrando para longe, que é o Lync Server 2013 ou o Skype for Business Server 2015.
    
## <a name="in-this-section"></a>Nesta seção

- [Antes de começar a migração](before-you-begin-the-migration.md)
    
- [Fase 1: Planejar sua migração](phase-1-plan-your-migration.md)
    
- [Fase 2: Preparar para migração](phase-2-prepare-for-migration.md)
    
- [Fase 3: Implantar pool piloto](phase-3-deploy-pilot-pool.md)
    
- [Fase 4: mover os usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Etapa 5: Adicionar Servidor de Borda ao pool piloto](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Fase 6: Mover da implantação piloto para produção](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Fase 7: Concluir tarefas pós-migração](phase-7-complete-post-migration-tasks.md)
    
- [Fase 8: Encerrar os pools herdados](phase-8-decommission-legacy-pools.md)
    

