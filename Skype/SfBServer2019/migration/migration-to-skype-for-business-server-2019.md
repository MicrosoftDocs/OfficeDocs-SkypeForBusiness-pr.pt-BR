---
title: Migração para Skype for Business Server 2019
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Os tópicos desta seção orientam você pelo processo de migração para Skype for Business Server 2019.
ms.openlocfilehash: 6eb192c11ec8d1f44539e3bd5180249d85180d2b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587973"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migração para Skype for Business Server 2019

Os tópicos desta seção orientam você pelo processo de migração para Skype for Business Server 2019. Este artigo aborda a migração do Lync Server 2013 ou Skype for Business Server 2015 para Skype for Business Server 2019.

> [!IMPORTANT]
> Em todo o conteúdo, usamos o termo *legado* para se referir ao Lync Server 2013 ou Skype for Business Server 2015 herdado que você está migrando para Skype for Business Server 2019.
  
> [!IMPORTANT]
> Este guia descreve as etapas geralmente necessárias para realizar cada fase de migração. Ele não atende todas as topologias de implantação herdada possíveis ou todos os cenários de migração possíveis. Portanto, talvez não seja necessário executar cada etapa descrita, ou talvez seja necessário executar etapas adicionais, dependendo de sua implantação. Este guia também fornece exemplos de etapas de verificação. Essas etapas de verificação são fornecidas para ajudá-lo a entender o que você precisa procurar para garantir que cada fase seja concluída com êxito à medida que você progride em sua migração. Personalize estas etapas de verificação para seu processo de migração específico. 
  
Este guia oferece informações específicas para atualizar sua implantação existente. Ele não explica como alterar sua topologia existente. O documento também não aborda a implementação de novos recursos. Quando um procedimento detalhado é documentado em outro lugar, este guia direciona você para a seção artigo ou artigo. 
  
Este artigo define os termos conforme especificado na lista a seguir.
  
**migração:** Movendo sua implantação de produção do Lync Server 2013 ou Skype for Business Server 2015 para Skype for Business Server 2019.
    
**coexistência:** O ambiente temporário que existe durante a migração quando alguma funcionalidade foi migrada para o Skype for Business Server 2019 e outras funcionalidades ainda permanecem em uma versão anterior.
    
**interoperabilidade:** A capacidade de sua implantação operar com êxito durante o período de coexistência.

**legacy:** O sistema do qual você está migrando, que é o Lync Server 2013 ou Skype for Business Server 2015.
    
## <a name="in-this-section"></a>Nesta seção

- [Antes de começar a migração](before-you-begin-the-migration.md)
    
- [Fase 1: Planejar sua migração](phase-1-plan-your-migration.md)
    
- [Fase 2: Preparar para migração](phase-2-prepare-for-migration.md)
    
- [Fase 3: Implantar pool piloto](phase-3-deploy-pilot-pool.md)
    
- [Fase 4: Mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Etapa 5: Adicionar Servidor de Borda ao pool piloto](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Fase 6: Mover da implantação piloto para produção](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Fase 7: Concluir tarefas pós-migração](phase-7-complete-post-migration-tasks.md)
    
- [Fase 8: Encerrar os pools herdados](phase-8-decommission-legacy-pools.md)
    

