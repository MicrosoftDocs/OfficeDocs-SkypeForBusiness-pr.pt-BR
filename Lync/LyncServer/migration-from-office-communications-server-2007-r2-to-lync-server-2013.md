---
title: Migração do Office Communications Server 2007 R2 para o Lync Server 2013
description: Migração do Office Communications Server 2007 R2 para o Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0afdc754ae691bc674c200addb9fb97c1eb4199
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569587"
---
# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Migração do Office Communications Server 2007 R2 para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Os tópicos desta seção orientam você durante o processo de migração do Office Communications Server 2007 R2 para o Lync Server 2013

<div>


> [!IMPORTANT]  
> Este documento descreve as etapas geralmente necessárias para realizar cada fase de migração. Não resolve todos os cenários de migração possíveis ou de topologia de implantação herdada. Portanto, você pode não precisar realizar cada etapa descrita ou pode precisar realizar etapas adicionais, dependendo da sua implantação. Este documento também oferece exemplos de etapas de verificação. Estas etapas de verificação são oferecidas para ajudar na compreensão do que é necessário procurar para garantir que cada fase seja concluída com êxito conforme você progride na sua implantação. Personalize estas etapas de verificação para seu processo de migração específico.



</div>

Este guia oferece informações específicas para atualizar sua implantação existente. Explica como alterar sua topologia existente. Este guia não aborda a implementação de novos recursos. Quando um procedimento detalhado é documentado em outro local, este guia orienta você para o documento ou seção adequado.

Este documento define os termos conforme especificados na lista a seguir.

  - *migração*  
    Mover sua implantação de produção de uma versão anterior do Office Communications Server 2007 R2 para o Lync Server 2013.

<!-- end list -->

  - *atualização*  
    Instalação de uma versão mais recente de software em um servidor ou computador cliente.

<!-- end list -->

  - *coexistência*  
    O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Lync Server 2013 e outras funcionalidades ainda permanecem em uma versão anterior do Office Communications Server 2007 R2.

<!-- end list -->

  - *interoperabilidade*  
    A capacidade da sua implantação operar com êxito durante o período de coexistência.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Antes de começar a migração](before-you-begin-the-migration.md)

  - [Fases de migração](migration-phases.md)

  - [Fase 1: planejar a migração do Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Fase 2: Preparar para migração](phase-2-prepare-for-migration.md)

  - [Fase 3: implantar o pool piloto do Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Fase 4: mesclar topologias](phase-4-merge-topologies.md)

  - [Fase 5: configurar o pool piloto](phase-5-configure-the-pilot-pool.md)

  - [Fase 6: mover usuários para o pool piloto](phase-6-move-users-to-the-pilot-pool.md)

  - [Fase 7: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 8: mover da implantação piloto para a produção](phase-8-move-from-pilot-deployment-into-production.md)

  - [Fase 9: concluir tarefas de migração](phase-9-complete-post-migration-tasks.md)

  - [Fase 10: encerrar o site herdado](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

