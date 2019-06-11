---
title: 'Lync Server 2013: Suporte a Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9be3bda71e44d0e739fce3a8d01db9cb84e2b9e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Suporte a Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-12-04_

As topologias locais dos serviços de domínio Active Directory com suporte no Lync Server 2013 são as seguintes:

  - Floresta única com domínio único

  - Floresta única com uma única árvore e vários domínios

  - Floresta única com várias árvores e namespaces não contíguos

  - Várias florestas em uma topologia de floresta central

  - Várias florestas em uma topologia de floresta de recursos

<div>


> [!NOTE]  
> O Lync Server 2013 não é compatível com domínios de rótulo único. Por exemplo, uma floresta com um domínio raiz chamado <STRONG>contoso. local</STRONG> tem suporte, mas não há suporte para um domínio raiz de rótulo único chamado <STRONG>local</STRONG> . Para obter detalhes, consulte o artigo 300684 da base de dados de conhecimento Microsoft, "informações sobre como configurar o Windows para domínios com <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>nomes DNS de rótulo único" em.



</div>

<div>


> [!NOTE]  
> O Lync Server 2013 não é compatível com a renomeação de domínios. Se você precisar renomear um domínio onde o Lync Server está implantado, primeiro você precisa desinstalar o Lync Server, depois renomear o domínio e depois reinstalar o Lync Server.



</div>

Para obter detalhes sobre topologias e requisitos compatíveis para implantações locais, consulte [requisitos, suporte e topologias de serviços de domínio do Active Directory no Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) na documentação de planejamento.

</div>

<span> </span>

</div>

</div>

</div>

