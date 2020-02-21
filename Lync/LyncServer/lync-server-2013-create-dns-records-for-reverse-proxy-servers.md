---
title: 'Lync Server 2013: criar registros DNS para servidores de proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79c583f5c25ea58f0d1a2ea32246db8eec8f7740
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Criar registros DNS para servidores de proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-29_

Crie registros DNS externos A que apontam para a interface externa pública do seu Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 servidor ou roteamento de solicitação de aplicativo do servidor de informações da Internet, conforme descrito em [Configure DNS for Edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md). Você precisa de registros DNS para os FQDNs do serviço Web externo para cada pool, o diretor (ou pool de diretores) e cada URL simples.

É necessário criar os seguintes registros para os registros DNS mínimos para a resolução de cliente do proxy reverso:

  - (S) registro (s) do host (A) que definem os serviços Web externos publicados para diretores e pools de diretores (por exemplo, **webdirext.contoso.com**)

  - (S) registro (s) do host (A) que definem os serviços Web externos publicados para serviços Web externos hospedados em qualquer pool de front-ends e nas funções de servidor Standard Edition (por exemplo, **webext.contoso.com**)

  - Registros do host (A) para os URLs simples (por exemplo, **dialin.contoso.com** e **meet.contoso.com**)

  - Registro de host (A) para o registro externo de descoberta do Lync e também fornece um ponteiro para descoberta automática para todos os aplicativos Web, incluindo o Lync Web App, o Agendador e a mobilidade (por exemplo, **lyncdiscover.contoso.com**)

  - Registros de host (A) para a URL do servidor do Office Web Apps (por exemplo, **officewebapp01.contoso.com**)

Para obter detalhes, consulte [DNS Summary-reverso proxy no Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

</div>

<span> </span>

</div>

</div>

</div>

