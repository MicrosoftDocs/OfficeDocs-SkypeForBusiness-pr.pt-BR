---
title: 'Lync Server 2013: Criar registros de DNS para servidores de proxy reverso'
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
ms.openlocfilehash: 0f85b222688dcefd45030f2c05f7b59ce45ec0ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Criar registros de DNS para servidores de proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-29_

Criar registros DNS externos A que apontam para a interface pública pública do seu Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server ou serviço de solicitação de aplicativo do servidor de informações da Internet, conforme descrito em [Configurar o suporte a DNS para Edge no Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md). Você precisa de registros de DNS para os FQDNs do serviço Web externo para cada pool, o diretor (ou o pool de directors) e cada URL simples.

Os registros DNS mínimos para a resolução do cliente para o proxy reverso, os seguintes registros devem ser criados:

  - Registro (s) do host (A) que define os serviços Web externos publicados para directors e pools de directors (por exemplo, **webdirext.contoso.com**)

  - Registros de host (A) que definem os serviços Web externos publicados para serviços Web externos hospedados em todas as funções de servidor front-end e Standard Edition (por exemplo, **webext.contoso.com**)

  - Registros de host (A) para URLs simples (por exemplo, **dialin.contoso.com** e **Meet.contoso.com**)

  - Registro de host (A) para o registro externo de descoberta do Lync e também fornece o ponteiro para descoberta automática para todos os aplicativos Web, incluindo o Lync Web App, o Agendador e a mobilidade (por exemplo, **lyncdiscover.contoso.com**)

  - Registros de host (A) para a URL do servidor dos Office Web Apps (por exemplo, **officewebapp01.contoso.com**)

Para obter detalhes, consulte [Resumo DNS-proxy reverso no Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

</div>

<span> </span>

</div>

</div>

</div>

