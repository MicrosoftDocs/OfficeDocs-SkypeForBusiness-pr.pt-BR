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
ms.openlocfilehash: 0688fc80bb763a4b5aa3e7ff10970cef96465b84
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Migração do Lync Server 2010 para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-17_

Os tópicos desta seção orientam você durante o processo de migração do Lync Server 2010 para o Lync Server 2013.

<div>


> [!IMPORTANT]  
> Este documento descreve as etapas geralmente necessárias para realizar cada fase de migração. Não resolve todos os cenários de migração possíveis ou de topologia de implantação herdada. Portanto, você pode não precisar realizar cada etapa descrita ou pode precisar realizar etapas adicionais, dependendo da sua implantação. Este documento também oferece exemplos de etapas de verificação. Estas etapas de verificação são oferecidas para ajudar na compreensão do que é necessário procurar para garantir que cada fase seja concluída com êxito conforme você progride na sua implantação. Personalize estas etapas de verificação para seu processo de migração específico.



</div>

Este guia oferece informações específicas para atualizar sua implantação existente. Explica como alterar sua topologia existente. Este guia não aborda a implementação de novos recursos. Quando um procedimento detalhado é documentado em outro local, este guia orienta você para o documento ou seção adequado.

Este documento define os termos conforme especificados na lista a seguir.

  - *migração*  
    Mover sua implantação de produção de uma versão anterior do Lync Server 2010 para o Lync Server 2013.

<!-- end list -->

  - *atualização*  
    Instalação de uma versão mais recente de software em um servidor ou computador cliente.

<!-- end list -->

  - *coexistência*  
    O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Lync Server 2013 e outras funcionalidades ainda permanecem em uma versão anterior do Lync Server 2010.

<!-- end list -->

  - *interoperabilidade*  
    A capacidade da sua implantação operar com êxito durante o período de coexistência.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Antes de começar a migração](before-you-begin-the-migration.md)

  - [Fase 1: planejar a migração do Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Fase 2: preparar-se para a migração](phase-2-prepare-for-migration.md)

  - [Fase 3: implantar o pool piloto do Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Fase 5: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 6: mover da implantação piloto para a produção](phase-6-move-from-pilot-deployment-into-production.md)

  - [Fase 7: concluir tarefas de migração](phase-7-complete-post-migration-tasks.md)

  - [Fase 8: encerrar pools herdados](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

