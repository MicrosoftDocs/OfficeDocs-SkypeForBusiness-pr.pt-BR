---
title: 'Lync Server 2013: Preparando Serviços de Domínio Active Directory bloqueado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 482c5a59c6dc53fc712db7e77430367dd9c37af5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="03e8d-102">Preparando Serviços de Domínio Active Directory bloqueado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03e8d-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03e8d-103">_**Tópico da última modificação:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="03e8d-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="03e8d-104">Geralmente, as organizações bloqueiam os serviços de domínio do Active Directory para ajudar a reduzir os riscos de segurança.</span><span class="sxs-lookup"><span data-stu-id="03e8d-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="03e8d-105">No entanto, um ambiente do Active Directory bloqueado pode limitar as permissões exigidas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03e8d-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="03e8d-106">A preparação adequada de um ambiente do Active Directory bloqueado para o Lync Server 2013 envolve algumas considerações e etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="03e8d-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="03e8d-107">Duas maneiras comuns nas quais as permissões são limitadas em um ambiente bloqueado do Active Directory são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="03e8d-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="03e8d-108">As entradas de controle de acesso do usuário autenticado (ACEs) são removidas dos contêineres.</span><span class="sxs-lookup"><span data-stu-id="03e8d-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="03e8d-109">A herança de permissões está desabilitada em contêineres de objetos de usuário, contato, InetOrgPerson ou computador.</span><span class="sxs-lookup"><span data-stu-id="03e8d-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="03e8d-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="03e8d-110">In This Section</span></span>

  - [<span data-ttu-id="03e8d-111">Permissões de usuário autenticado são removidas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03e8d-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="03e8d-112">Herança de permissões está desabilitado em computadores, usuários ou contêiners InetOrgPerson no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03e8d-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

