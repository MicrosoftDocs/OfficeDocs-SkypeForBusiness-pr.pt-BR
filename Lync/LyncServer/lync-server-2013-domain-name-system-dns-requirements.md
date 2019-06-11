---
title: 'Lync Server 2013: requisitos de DNS (sistema de nomes de domínio)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771bf78f8477008345422cc61f63202c58fcdd14
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Requisitos do sistema de nomes de domínio (DNS) para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-18_

Para implantar o Lync Server, você deve criar registros de sistema de nome de domínio (DNS) que permitem a descoberta de clientes e servidores e, opcionalmente, suporte para entrada automática de cliente se a sua organização quiser dar suporte a ele.

O Lync Server usa o DNS das seguintes maneiras:

  - Para descobrir servidores internos ou pools para comunicações entre servidores.

  - Para permitir que os clientes descubram o pool de front-end ou o servidor Standard Edition usado para várias transações SIP.

  - Para permitir que dispositivos de comunicação unificada (UC) não estejam conectados para descobrir o pool de front-end ou o servidor Standard Edition executando o serviço Web de atualização de dispositivos, obtenha atualizações e envie logs.

  - Para permitir que servidores e clientes externos se conectem a servidores de borda ou ao proxy reverso HTTP para mensagens instantâneas (IM) ou conferência.

  - Para permitir que dispositivos de comunicação unificada externos se conectem ao serviço Web de atualização de dispositivo por meio de servidores de borda ou do proxy reverso HTTP e obtenham atualizações

  - Para permitir que os clientes móveis descubram automaticamente os recursos de serviços Web sem exigir que os usuários insiram manualmente URLs nas configurações do dispositivo.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Determinar requisitios de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Requisitos de DNS para pools front-end no Lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Requisitos de DNS para servidores de edição padrão no Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Requisitos de DNS para URLs simples no Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisitos de DNS para entrada automática do cliente no Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Requisitos de DNS para mobilidade com o Lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [Balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

