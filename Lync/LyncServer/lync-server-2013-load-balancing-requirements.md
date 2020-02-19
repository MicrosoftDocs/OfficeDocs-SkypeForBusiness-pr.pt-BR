---
title: Requisitos de balanceamento de carga do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83e5ebe92601b839f50604a93f10f7fc2f5d7deb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Requisitos de balanceamento de carga para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

Se você tiver pools de front-ends, pools de diretores ou servidores de borda, será necessário implantar o balanceamento de carga para esses pools. O balanceamento de carga distribui o tráfego entre os servidores em um pool.

O Lync Server 2013 oferece suporte a dois tipos de soluções de balanceamento de carga para tráfego de cliente para servidor: balanceamento de carga DNS (sistema de nomes de domínio) e balanceamento de carga de hardware. O balanceamento de carga DNS oferece várias vantagens, incluindo administração mais simples, solução de problemas mais eficiente e a capacidade de isolar grande parte do tráfego do Lync Server de qualquer problema potencial de balanceador de carga de hardware.

Decida que solução de balanceamento de carga é apropriada para cada pool de sua implantação, considerando as seguintes restrições:

  - A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS em uma interface e o balanceamento de carga de hardware em outra.

  - Alguns tipos de tráfego exigem um balanceador de carga de hardware. Por exemplo, o tráfego HTTP requer um balanceador de carga de hardware em vez do balanceamento de carga DNS. O balanceamento de carga DNS não funciona com o tráfego web de cliente-servidor.

Para obter mais detalhes sobre a escolha de uma solução de balanceador de carga de hardware, consulte [requisitos de balanceador de carga de hardware para o Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Se você optar por usar o balanceamento de carga DNS para um pool mas ainda precisa implementar balanceadores de carga de hardware para o tráfego, como o tráfego HTTP, a administração dos balanceadores de carga de hardware é bastante simplificada. Por exemplo, a configuração do balanceador de carga de hardware será mais simples, pois só gerenciará o tráfego HTTP e HTTPS, enquanto todos os outros protocolos serão gerenciados pelo balanceamento de carga DNS. Para obter detalhes, consulte [balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md).

Para o tráfego de servidor para servidor, o Lync Server 2013 usa o balanceamento de carga com reconhecimento de topologia. Os servidores lêem a topologia publicada no repositório de gerenciamento central para obter os FQDNs dos servidores na topologia e distribuir automaticamente o tráfego entre os servidores. Os administradores não precisam configurar ou gerenciar esse tipo de balanceamento de carga.

Se você usar o balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas de endereço IP do FQDN do pool. Você também deve remover a entrada DNS do computador.

</div>

<span> </span>

</div>

</div>

</div>

