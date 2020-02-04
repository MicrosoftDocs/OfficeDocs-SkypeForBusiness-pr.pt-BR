---
title: 'Lync Server 2013: Componentes usados pelo aplicativo Comunicado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52ef0b1da665f8797f29582e9ce9e1d311287d61
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Componentes usados pelo aplicativo Comunicado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-13_

No Lync Server 2013, o aplicativo de anúncio é um componente do aplicativo de grupo de resposta. Quando você implanta o Enterprise Voice, o aplicativo de anúncio é automaticamente instalado e ativado juntamente com o aplicativo de grupo de resposta. Esta seção descreve os componentes que dão suporte ao aplicativo de anúncio.

<div>

## <a name="announcement-application-components"></a>Componentes do aplicativo de anúncio

Os seguintes componentes do Lync Server são compatíveis com o aplicativo de anúncio:

  - ****   Serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantação, hospedagem e gerenciamento de aplicativos de comunicação unificada. O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool Front-end e em cada servidor Standard Edition.

  - **Aplicativo de grupo de resposta**   o aplicativo grupo de resposta é um dos aplicativos de comunicação unificada hospedados pelo serviço de aplicativo. Quando um intervalo de números de telefone não atribuído está configurado para direcionar para um comunicado, o aplicativo grupo de resposta é necessário para direcionar as chamadas feitas para o número de telefone. (O aplicativo de grupo de resposta não será necessário se todos os intervalos estiverem configurados para direcionar a UM (a) Unificação de mensagens do Exchange.)

  - **Arquivos de áudio**   os arquivos de áudio são usados para os comunicados.

  - **Repositório de arquivos**   o aplicativo de anúncio usa o repositório de arquivos para armazenar seus arquivos de áudio.

  - **Painel de controle do Lync Server**   você pode usar o painel de controle do Lync Server para configurar a tabela numérica não atribuída.

  - **Shell de gerenciamento do Lync Server**   você pode usar cmdlets do Shell de gerenciamento do Lync Server para definir as configurações de anúncio e a tabela de número não atribuído.

</div>

</div>

<span> </span>

</div>

</div>

</div>

