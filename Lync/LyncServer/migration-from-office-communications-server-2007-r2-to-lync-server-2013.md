---
title: Migração do Office Communications Server 2007 R2 para Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43064d265bc08cab3721d0f19fd7f89184871f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Migração do Office Communications Server 2007 R2 para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Os tópicos desta seção guiam você pelo processo de migração do Office Communications Server 2007 R2 para o Lync Server 2013

<div>


> [!IMPORTANT]  
> Este documento descreve as etapas geralmente necessárias para realizar cada fase da migração. Ele não trata cada possível topologia de implantação herdada ou todos os possíveis cenários de migração. Portanto, talvez você não precise executar todas as etapas descritas ou talvez seja necessário executar etapas adicionais, dependendo da sua implantação. Este documento também fornece exemplos de etapas de verificação. Estas etapas de verificação são fornecidas para ajudá-lo a entender o que você precisa procurar para garantir que cada fase seja concluída com êxito enquanto avança pela migração. Personalize essas etapas de verificação para seu processo de migração específico.



</div>

Este guia fornece informações específicas para atualizar sua implantação existente. Ele não explica como alterar a topologia existente. Este guia não aborda a implementação de novos recursos. Quando um procedimento detalhado for documentado em outro lugar, este guia direcionará você para a seção do documento ou documento apropriado.

Este documento define termos conforme especificado na lista a seguir.

  - *migração*  
    Mover a implantação de produção de uma versão anterior do Office Communications Server 2007 R2 para o Lync Server 2013.

<!-- end list -->

  - *atualização*  
    Instalar uma versão mais recente do software em um computador cliente ou servidor.

<!-- end list -->

  - *coexistência*  
    O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Lync Server 2013 e outras funcionalidades ainda permanecem em uma versão anterior do Office Communications Server 2007 R2.

<!-- end list -->

  - *interoperabilidade*  
    A capacidade de sua implantação operar com sucesso durante o período de coexistência.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Antes de começar a migração](before-you-begin-the-migration_1.md)

  - [Fases de migração](migration-phases_1.md)

  - [Fase 1: planejar a migração do Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Fase 2: Preparar para migração](phase-2-prepare-for-migration_1.md)

  - [Fase 3: implantar o pool piloto do Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Fase 4: topologias de mesclagem](phase-4-merge-topologies.md)

  - [Fase 5: configurar o pool piloto](phase-5-configure-the-pilot-pool.md)

  - [Fase 6: mover usuários para o pool piloto](phase-6-move-users-to-the-pilot-pool.md)

  - [Fase 7: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 8: mover da implantação piloto para produção](phase-8-move-from-pilot-deployment-into-production.md)

  - [Fase 9: concluir tarefas posteriores à migração](phase-9-complete-post-migration-tasks.md)

  - [Fase 10: descomissionar site herdado](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

