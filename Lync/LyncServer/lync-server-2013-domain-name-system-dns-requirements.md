---
title: 'Lync Server 2013: requisitos de DNS (sistema de nomes de domínio)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2536e5079009d508765055d31e80efb1b998aa0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Requisitos de DNS (sistema de nomes de domínio) para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-18_

Para implantar o Lync Server, você deve criar registros de DNS (sistema de nomes de domínio) que permitem a descoberta de clientes e servidores, e, opcionalmente, suporte para entrada automática de cliente se sua organização quiser oferecer suporte a ele.

O Lync Server usa o DNS das seguintes maneiras:

  - Para descobrir pools ou servidores internos para a comunicação entre servidores.

  - Para permitir que os clientes descubram o pool de front-ends ou o servidor Standard Edition usado para várias transações SIP.

  - Para permitir que os dispositivos UC (comunicações unificadas) que não estão conectados descubram o pool de front-ends ou o servidor Standard Edition executando o serviço Web de atualização de dispositivo, obtenham atualizações e enviem logs.

  - Para permitir que servidores e clientes externos se conectem aos servidores de borda ou ao proxy reverso HTTP para mensagens instantâneas (IM) ou de conferência.

  - Para permitir que os dispositivos de UC externos se conectem ao serviço Web de atualização de dispositivo por meio de servidores de borda ou do proxy reverso HTTP e obtenham atualizações.

  - Para permitir que clientes móveis descubram automaticamente os recursos dos Serviços Web sem exigir que os usuários insiram URLs manualmente nas configurações do dispositivo.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Requisitos de DNS para pools de front-ends no Lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Requisitos de DNS para servidores Standard Edition no Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Requisitos de DNS para URLs simples no Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisitos de DNS para entrada de cliente automática no Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Requisitos de DNS para mobilidade com o Lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [Balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

