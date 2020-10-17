---
title: 'Lync Server 2013: preparando os serviços de domínio do Active Directory bloqueado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b3e1eb33568bbc0e1742e31638a20879e4fffdd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513358"
---
# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>Preparando os serviços de domínio do Active Directory bloqueados no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-05-14_

As organizações geralmente bloqueiam os serviços de domínio do Active Directory para ajudar a reduzir os riscos de segurança. No entanto, um ambiente do Active Directory bloqueado pode limitar as permissões exigidas pelo Lync Server 2013. A preparação adequada de um ambiente do Active Directory bloqueado para o Lync Server 2013 envolve algumas considerações e etapas adicionais.

As permissões estão limitadas em um ambiente de Active Directory bloqueado de duas maneiras:

  - As ACEs (entradas de controle de acesso) de usuários autenticados são removidas dos contêineres.

  - A herança de permissões está desabilitada nos contêineres de objetos de Usuário, Contato, InetOrgPerson ou Computador.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [As permissões de usuário autenticado são removidas no Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [A herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson no Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

