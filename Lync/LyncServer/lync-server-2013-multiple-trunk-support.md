---
title: 'Lync Server 2013: suporte a vários troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 273ab81fc0ab3fce9daae56abc6dc68b89489371
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a>Suporte a vários troncos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

A funcionalidade do Lync Server 2013 oferece suporte a várias associações entre gateways e servidores de mediação. Essas associações são feitas por meio da definição de um tronco, que é uma associação lógica entre um pool de servidor de mediação e um gateway PSTN (controlador de borda de sessão), SBC ou IP-PBX. Use o construtor de topologia para associar gateways a servidores de mediação (ou seja, troncos).

  - Para atribuir ou remover um tronco no Lync Server 2013, primeiro você deve definir um tronco no construtor de topologia. Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do servidor de mediação, a porta de escuta do servidor de mediação, o FQDN do gateway e a porta de escuta do gateway.

  - Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação. Isso fornece resiliência adicional para a infraestrutura do Enterprise Voice, que é especialmente útil em cenários de interoperabilidade de PBX (Private Branch Exchange).

Quando um tronco é definido, ele deve ser associado a uma rota. Para associar um tronco a uma rota, você define um nome simples para o tronco no construtor de topologias. Esse nome simples é usado como o nome do tronco no painel de controle do Lync Server, onde os troncos podem ser associados a rotas. O nome do tronco simples é usado como o nome do gateway no Shell de gerenciamento do Lync Server.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

O administrador deve selecionar um tronco padrão associado a um servidor de mediação. No construtor de topologias, clique com o botão direito do mouse no servidor de mediação associado e clique em **Propriedades**. Especifique o gateway padrão para o servidor de mediação.

O diagrama a seguir ilustra os vários troncos definidos para cada servidor de mediação e gateway.

**Roteamento de tronco M-N**

![Várias atribuições de tronco.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Várias atribuições de tronco.")

</div>

<span> </span>

</div>

</div>

</div>

