---
title: Migração do Lync Server 2010 para o Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c32d2679d4f31863e389735efb6660ea670b959
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Migração do Lync Server 2010 para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-17_

Os tópicos desta seção guiam você pelo processo de migração do Lync Server 2010 para o Lync Server 2013.

<div>


> [!IMPORTANT]  
> Este documento descreve as etapas geralmente necessárias para realizar cada fase da migração. Ele não trata cada possível topologia de implantação herdada ou todos os possíveis cenários de migração. Portanto, talvez você não precise executar todas as etapas descritas ou talvez seja necessário executar etapas adicionais, dependendo da sua implantação. Este documento também fornece exemplos de etapas de verificação. Estas etapas de verificação são fornecidas para ajudá-lo a entender o que você precisa procurar para garantir que cada fase seja concluída com êxito enquanto avança pela migração. Personalize essas etapas de verificação para seu processo de migração específico.



</div>

Este guia fornece informações específicas para atualizar sua implantação existente. Ele não explica como alterar a topologia existente. Este guia não aborda a implementação de novos recursos. Quando um procedimento detalhado for documentado em outro lugar, este guia direcionará você para a seção do documento ou documento apropriado.

Este documento define termos conforme especificado na lista a seguir.

  - *migração*  
    Mover a implantação de produção de uma versão anterior do Lync Server 2010 para o Lync Server 2013.

<!-- end list -->

  - *atualização*  
    Instalar uma versão mais recente do software em um computador cliente ou servidor.

<!-- end list -->

  - *coexistência*  
    O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Lync Server 2013 e outras funcionalidades ainda permanecem em uma versão anterior do Lync Server 2010.

<!-- end list -->

  - *interoperabilidade*  
    A capacidade de sua implantação operar com sucesso durante o período de coexistência.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Antes de começar a migração](before-you-begin-the-migration.md)

  - [Fase 1: planejar a migração do Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Fase 2: Preparar para migração](phase-2-prepare-for-migration.md)

  - [Fase 3: implantar o pool piloto do Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Fase 4: mover os usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Fase 5: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 6: Mover da implantação piloto para produção](phase-6-move-from-pilot-deployment-into-production.md)

  - [Fase 7: Concluir tarefas pós-migração](phase-7-complete-post-migration-tasks.md)

  - [Fase 8: Encerrar os pools herdados](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

