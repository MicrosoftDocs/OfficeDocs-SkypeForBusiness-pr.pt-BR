---
title: 'Lync Server 2013: componentes usados pelo estacionamento de chamadas'
description: 'Lync Server 2013: componentes usados pelo estacionamento de chamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285af316fa2d49e8bebf68e11de6d9526e12ae29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576767"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a>Componentes usados pelo estacionamento de chamadas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-13_

O aplicativo de estacionamento de chamada é instalado automaticamente quando você implanta o Enterprise Voice. Habilite o estacionamento de chamadas Configurando a política de voz. Os seguintes componentes do Lync Server 2013 suportam o aplicativo de estacionamento de chamada:

  - **Serviço**     de aplicativo O serviço de aplicativo fornece uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicação unificada, como o aplicativo de estacionamento de chamada. O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool de front-ends e em cada servidor Standard Edition.

  - Aplicativo de estacionamento de **chamada**     O aplicativo de estacionamento de chamada é um dos aplicativos de comunicações unificadas hospedados pelo serviço de aplicativo. Ele é incluído automaticamente quando você implanta o Enterprise Voice. Parques de estacionamento de chamada e recupera chamadas e gerencia órbitas de estacionamento de chamadas.

  - Arquivos de música **em espera**     Se a música estiver habilitada, o arquivo de música será tocado enquanto uma chamada estiver estacionada. Um arquivo de música padrão é incluído quando o aplicativo de estacionamento de chamada é instalado.

  - **Repositório**     de arquivos O aplicativo de estacionamento de chamada usa o repositório de arquivos para armazenar arquivos de áudio personalizados.

  - Painel de controle **do Lync Server**     Você pode usar o painel de controle do Lync Server para configurar a tabela de órbita de estacionamento de chamada e para habilitar o estacionamento de chamada para os usuários.

  - Shell de gerenciamento **do Lync Server**     Todas as configurações de aplicativo de estacionamento de chamadas podem ser realizadas usando os cmdlets do Shell de gerenciamento do Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

