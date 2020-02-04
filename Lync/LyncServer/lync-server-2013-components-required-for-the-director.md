---
title: 'Lync Server 2013: Componentes necessários para o diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Componentes necessários para o diretor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

O único componente necessário para criar e configurar um diretor é implantar a função de servidor diretor. Isso é feito usando o construtor de topologias e define um único pool de computadores ou um pool de vários computadores no nó do pool de diretor. Depois de definir o diretor ou o pool do diretor, execute o assistente de implantação do Lync Server no computador que será um diretor. No caso de um pool de diretor, você executa o assistente de implantação do Lync Server em cada servidor que será membro do pool.

<div>

## <a name="topologies"></a>Topologia

Você pode implementar um único servidor de director ou um pool de directors. O diretor é sempre um servidor ou pool separado, não posicionado com nenhuma outra função de servidor no Lync Server 2013.

<div>


> [!NOTE]  
> Se você não implantar diretores, o servidor front-end ou o pool de front-end assumirá a função de diretor.



</div>

É necessário balancear A carga de um pool de diretores. Você pode executar uma das seguintes ações:

  - Crie uma topologia que use um balanceador de carga de hardware para serviços Web e balanceamento de carga DNS (Domain Name System) para os outros tipos de tráfego.
    
    [Pool de diretores em escala - balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Crie uma topologia que use um balanceador de carga de hardware para o balanceamento de carga necessário para o pool de diretor.
    
    [Pool de diretores em escala - balanceador de carga de hardware no Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

