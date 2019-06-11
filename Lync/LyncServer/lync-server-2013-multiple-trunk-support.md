---
title: 'Lync Server 2013: suporte a vários troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156db04ceb26809c7043f30e9e01ea0071e0a31d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a>Suporte a vários troncos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

A funcionalidade do Lync Server 2013 oferece suporte a várias associações entre gateways e servidores de mediação. Essas associações são feitas pela definição de um tronco, que é uma associação lógica entre um pool do servidor de mediação e um gateway de rede telefônica pública comutada (SBC), ou PBX IP. Use o construtor de topologias para associar gateways a servidores de mediação (ou seja, troncos).

  - Para atribuir ou remover um tronco no Lync Server 2013, primeiro você deve definir um tronco no construtor de topologias. Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do servidor de mediação, a porta de escuta do servidor de mediação, o FQDN do gateway e a porta de escuta do gateway.

  - Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação. Isso fornece resiliência adicional à infraestrutura Enterprise Voice, que é especialmente útil em cenários de interoperabilidade de PBX (Private Branch Exchange).

Quando um tronco é definido, ele precisa ser associado à rota. Para associar um tronco a uma rota, você define um nome simples para o tronco no construtor de topologias. Esse nome simples é usado como o nome do tronco no painel de controle do Lync Server, em que os troncos podem ser associados às rotas. O nome do tronco simples é usado como o nome do gateway do Shell de gerenciamento do Lync Server.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

O administrador deve selecionar um tronco padrão associado a um servidor de mediação. No construtor de topologias, clique com o botão direito do mouse no servidor de mediação associado e, em seguida, clique em **Propriedades**. Especifique o gateway padrão do servidor de mediação.

O diagrama a seguir ilustra os vários troncos que são definidos para cada servidor e gateway de mediação.

**M-N roteamento de tronco**

![Várias atribuições de tronco.] (images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Várias atribuições de tronco.")

</div>

<span> </span>

</div>

</div>

</div>

