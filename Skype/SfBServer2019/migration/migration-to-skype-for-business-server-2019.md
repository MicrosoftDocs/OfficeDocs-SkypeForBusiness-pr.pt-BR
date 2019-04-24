---
title: Migração para o Skype para Business Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Os tópicos desta seção o orientam pelo processo de migração para o Skype para Business Server 2019.
ms.openlocfilehash: 32babd6fedd5defc756f73bbf001716c7c0b8a72
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231606"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migração para o Skype para Business Server 2019

Os tópicos desta seção o orientam pelo processo de migração para o Skype para Business Server 2019. Este artigo aborda como migrar do Lync Server 2013 ou Skype 2015 do servidor de negócios para Skype para Business Server 2019.

> [!IMPORTANT]
> Em todo o conteúdo, usamos o termo *herdado* para se referir ao antigo Lync Server 2013 ou Skype para Business Server 2015 que você está migrando para o Skype para Business Server 2019.
  
> [!IMPORTANT]
> Este guia descreve as etapas que geralmente necessárias para realizar cada fase da migração. Ele não aborda cada topologia de implantação herdada possíveis ou todos os cenários de migração possíveis. Portanto, você não precisará executar todas as etapas descritas, ou talvez você precise executar etapas adicionais, dependendo da sua implantação. Este guia também fornece exemplos das etapas de verificação. Essas etapas de verificação são fornecidas para ajudá-lo a entender o que você precisa para procurar para garantir que cada fase for concluída com êxito conforme você avança em sua migração. Adapte essas etapas de verificação para seu processo de migração específica. 
  
Este guia fornece informações específicas para atualização da implantação existente. Ele não explica como alterar a topologia existente. Este guia não aborda a implementação de novos recursos. Quando um procedimento detalhado está documentado em outro lugar, este guia direciona você para o artigo ou seção do artigo. 
  
Este artigo define termos conforme especificado na lista a seguir.
  
**migração:** Movendo sua implantação de produção do Lync Server 2013 ou Skype para Business Server 2015 para Skype para Business Server 2019.
    
**coexistência:** O ambiente temporário que existe durante a migração quando algumas funcionalidades podem tem sido migradas para Skype para Business Server 2019 e outra funcionalidade permanece na versão anterior.
    
**interoperabilidade:** A capacidade da sua implantação operar com êxito durante o período de coexistência.

**herdado:** O sistema migrar longe de, que é o Lync Server 2013 ou Skype para Business Server 2015.
    
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
    

