---
title: 'Lync Server 2013: colocação de servidor suportado para componentes de borda'
description: 'Lync Server 2013: colocação de servidor suportado para componentes de borda.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bf253e5210e077ca62b3d00f7f130d54d8392a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556357"
---
# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a>Colocação de servidor suportado para componentes de borda no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

O serviço de borda de acesso, o serviço de borda de webconferência, o serviço de borda A/V e o serviço de proxy do XMPP são colocados nos servidores de borda. Os servidores fornecem funções necessárias para o acesso de usuário externo e devem ser implantados como servidores dedicados:

  - Servidor de Borda

  - Diretor (opcional)

  - Proxy reverso

<div>


> [!IMPORTANT]  
> O proxy reverso não precisa ser dedicado para servir somente o Lync Server 2013. Por exemplo, você pode fornecer serviços para publicar os serviços Web do Lync Server e, simultaneamente, fornecer um site da Web publicado para outro site que não tenha nenhum rumo no Lync Server. Se você já tiver um servidor de proxy reverso na rede de perímetro para dar suporte a outros serviços, poderá usá-lo para o Lync Server 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

