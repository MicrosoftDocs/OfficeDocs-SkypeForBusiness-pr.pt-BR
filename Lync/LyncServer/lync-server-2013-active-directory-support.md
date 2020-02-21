---
title: Lync Server 2013 suporte ao Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a7da4487c376ceea4c5c3e41e20a55874b27f06
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Suporte do Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-04_

As topologias locais dos serviços de domínio Active Directory suportadas pelo Lync Server 2013 são as seguintes:

  - Floresta única com domínio único

  - Floresta única com uma única árvore e vários domínios

  - Floresta única com várias árvores e namespaces não contíguos

  - Várias florestas em uma topologia de floresta central

  - Várias florestas em uma topologia de floresta de recursos

<div>


> [!NOTE]  
> O Lync Server 2013 não dá suporte a domínios de rótulo único. Por exemplo, uma floresta com um domínio raiz chamado <STRONG>contoso. local</STRONG> é suportada, mas não há suporte para um domínio raiz de rótulo único chamado <STRONG>local</STRONG> . Para obter detalhes, consulte o artigo 300684 da base de dados de conhecimento da Microsoft, "informações sobre como configurar o Windows para domínios <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>com nomes DNS de rótulo único" em.



</div>

<div>


> [!NOTE]  
> O Lync Server 2013 não dá suporte à renomeação de domínios. Se for necessário renomear um domínio em que o Lync Server está implantado, primeiro você precisa desinstalar o Lync Server, renomear o domínio e, em seguida, reinstalar o Lync Server.



</div>

Para obter detalhes sobre as topologias e os requisitos suportados para implantações locais, consulte [Active Directory Domain Services requirements, support e topologias no Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) na documentação de planejamento.

</div>

<span> </span>

</div>

</div>

</div>

