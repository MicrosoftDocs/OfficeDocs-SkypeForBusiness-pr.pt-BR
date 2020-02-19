---
title: 'Lync Server 2013: componentes usados pelo recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05f41b7420f15c2815ababa0f85d8aca43898dd2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Componentes usados por recebimento de chamada em grupo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-30_

O recebimento de chamadas em grupo é implantado automaticamente quando você implanta o Enterprise Voice e o aplicativo de estacionamento de chamada. Você habilita o recebimento de chamadas em grupo Configurando a tabela de órbita de estacionamento de chamada com intervalos separados de números designados como números de grupo de recebimento de chamadas e, em seguida, atribuindo usuários para chamar grupos de retirada e habilitando os usuários para o recebimento de chamadas em grupo. Os seguintes componentes do Lync Server oferecem suporte ao recebimento de chamadas de Grupo:

  - ****   Serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicação unificada, como o aplicativo de estacionamento de chamada. O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool de front-ends e em cada servidor Standard Edition.

  - **Aplicativo de estacionamento de chamadas**   o aplicativo de estacionamento de chamada é um dos aplicativos de comunicações unificadas hospedados pelo serviço de aplicativo. O recebimento de chamadas em grupo é baseado no aplicativo de estacionamento de chamada.

  - **Shell de gerenciamento do Lync Server**   você usa o Shell de gerenciamento do Lync Server para gerenciar grupos de recebimento de chamadas de grupo.

  - **SEFAUtil Resource Kit Tool**   você usa o utilitário de ativação de recurso de extensão secundária (SEFAUtil) para atribuir usuários a um grupo de recebimento de chamadas e habilitar ou desabilitar o recebimento de chamadas para usuários.

</div>

<span> </span>

</div>

</div>

</div>

