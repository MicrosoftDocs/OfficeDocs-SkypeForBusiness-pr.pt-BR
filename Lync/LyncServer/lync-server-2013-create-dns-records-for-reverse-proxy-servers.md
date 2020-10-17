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
ms.openlocfilehash: 51af1c3179d8101a7e2f9942e15553b5831bce95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532208"
---
# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="fca71-102">Criar registros DNS para servidores de proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fca71-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fca71-103">_**Última modificação do tópico:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="fca71-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="fca71-104">Crie registros DNS externos A que apontam para a interface externa pública do seu Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 servidor ou roteamento de solicitação de aplicativo do servidor de informações da Internet, conforme descrito em [Configure DNS for Edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span><span class="sxs-lookup"><span data-stu-id="fca71-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="fca71-105">Você precisa de registros DNS para os FQDNs do serviço Web externo para cada pool, o diretor (ou pool de diretores) e cada URL simples.</span><span class="sxs-lookup"><span data-stu-id="fca71-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="fca71-106">É necessário criar os seguintes registros para os registros DNS mínimos para a resolução de cliente do proxy reverso:</span><span class="sxs-lookup"><span data-stu-id="fca71-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="fca71-107">(S) registro (s) do host (A) que definem os serviços Web externos publicados para diretores e pools de diretores (por exemplo, **webdirext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="fca71-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="fca71-108">(S) registro (s) do host (A) que definem os serviços Web externos publicados para serviços Web externos hospedados em qualquer pool de front-ends e nas funções de servidor Standard Edition (por exemplo, **webext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="fca71-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="fca71-109">Registros do host (A) para os URLs simples (por exemplo, **dialin.contoso.com** e **meet.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="fca71-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="fca71-110">Registro de host (A) para o registro externo de descoberta do Lync e também fornece um ponteiro para descoberta automática para todos os aplicativos Web, incluindo o Lync Web App, o Agendador e a mobilidade (por exemplo, **lyncdiscover.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="fca71-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="fca71-111">Registros de host (A) para a URL do servidor do Office Web Apps (por exemplo, **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="fca71-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="fca71-112">Para obter detalhes, consulte [DNS Summary-reverso proxy no Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="fca71-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

