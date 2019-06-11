---
title: 'Lync Server 2013: componentes usados pelo recurso de recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3583ee73c78a78317b1808bde395f76dcae85149
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Componentes usados pela retirada de chamadas em grupo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-30_

O recebimento de chamadas em grupo é implantado automaticamente quando você implanta o Enterprise Voice e o aplicativo de estacionamento de chamadas. Você permite o recebimento de chamadas em grupo Configurando a tabela órbita de estacionamento de chamada com intervalos separados de números designados como números de grupo de recebimento de chamadas e, em seguida, atribuindo aos usuários chamadas para grupos de retirada e habilitando os usuários para a retirada de chamadas em grupo. Os seguintes componentes do Lync Server suportam o recebimento de chamadas em grupo:

  - ****   Serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantação, hospedagem e gerenciamento de aplicativos de comunicação unificada, como o aplicativo de estacionamento de chamadas. O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool Front-end e em cada servidor Standard Edition.

  - **Aplicativo de estacionamento de chamadas**   o aplicativo de estacionamento de chamadas é um dos aplicativos de comunicação unificada hospedados pelo serviço de aplicativo. O recebimento de chamadas em grupo é baseado no aplicativo parque de chamadas.

  - **Shell de gerenciamento do Lync Server**   você usa o Shell de gerenciamento do Lync Server para gerenciar grupos de recebimento de chamadas em grupo.

  - **Ferramenta SEFAUtil Resource Kit**   você usa o utilitário de ativação de recursos de extensão secundária (SEFAUtil) para atribuir usuários a um grupo de recebimento de chamada e para habilitar ou desabilitar o recebimento de chamadas para usuários.

</div>

<span> </span>

</div>

</div>

</div>

