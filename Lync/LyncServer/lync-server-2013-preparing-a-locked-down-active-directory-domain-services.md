---
title: 'Lync Server 2013: preparando os serviços de domínio do Active Directory bloqueado'
description: 'Lync Server 2013: preparando os serviços de domínio do Active Directory bloqueados.'
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
ms.openlocfilehash: 4aea04b138de2630935713eda7cbef9e4d21572a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566297"
---
# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="1e19a-103">Preparando os serviços de domínio do Active Directory bloqueados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e19a-103">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e19a-104">_**Última modificação do tópico:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="1e19a-104">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="1e19a-105">As organizações geralmente bloqueiam os serviços de domínio do Active Directory para ajudar a reduzir os riscos de segurança.</span><span class="sxs-lookup"><span data-stu-id="1e19a-105">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="1e19a-106">No entanto, um ambiente do Active Directory bloqueado pode limitar as permissões exigidas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e19a-106">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="1e19a-107">A preparação adequada de um ambiente do Active Directory bloqueado para o Lync Server 2013 envolve algumas considerações e etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="1e19a-107">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="1e19a-108">As permissões estão limitadas em um ambiente de Active Directory bloqueado de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="1e19a-108">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="1e19a-109">As ACEs (entradas de controle de acesso) de usuários autenticados são removidas dos contêineres.</span><span class="sxs-lookup"><span data-stu-id="1e19a-109">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="1e19a-110">A herança de permissões está desabilitada nos contêineres de objetos de Usuário, Contato, InetOrgPerson ou Computador.</span><span class="sxs-lookup"><span data-stu-id="1e19a-110">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1e19a-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1e19a-111">In This Section</span></span>

  - [<span data-ttu-id="1e19a-112">As permissões de usuário autenticado são removidas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e19a-112">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="1e19a-113">A herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e19a-113">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

