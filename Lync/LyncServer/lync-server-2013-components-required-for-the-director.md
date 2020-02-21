---
title: 'Lync Server 2013: componentes necessários para o diretor'
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
ms.openlocfilehash: 84a5765ce21ba955e4354c693171180a9d828210
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Componentes necessários para o diretor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

O único componente necessário para criar e configurar um diretor é implantar a função de servidor diretor. Você faz isso usando o construtor de topologias e define um pool de computador único ou um pool de vários computadores no nó do pool de diretores. Após definir o diretor ou o pool de diretor, execute o assistente de implantação do Lync Server no computador que será um diretor. No caso de um pool de diretores, você executa o assistente de implantação do Lync Server em cada servidor que será membro do pool.

<div>

## <a name="topologies"></a>Topologias

Você pode implementar um único servidor de diretor ou um pool de diretores. O diretor é sempre um servidor ou pool separado, não colocado com qualquer outra função de servidor no Lync Server 2013.

<div>


> [!NOTE]  
> Se você não implantar diretores, o servidor front-end ou o pool de front-ends assumirá a função diretor.



</div>

Um pool de diretores deve ter o balanceamento de carga. Você pode:

  - Criar uma topologia que usa um balanceador de carga de hardware para serviços web e balanceamento de carga DNS (Domain Name System) para os outros tipos de tráfego.
    
    [Pool de diretores em escala-balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Criar uma topologia que usa um balanceador de carga de hardware para balanceamento de carga necessário para o pool de diretores.
    
    [Pool de diretores em escala-balanceador de carga de hardware no Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

