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
ms.openlocfilehash: 0181c2e4362685f8840af66d6a885c3e02611a85
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="ffa33-102">Preparando os serviços de domínio do Active Directory bloqueados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffa33-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffa33-103">_**Última modificação do tópico:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="ffa33-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="ffa33-104">As organizações geralmente bloqueiam os serviços de domínio do Active Directory para ajudar a reduzir os riscos de segurança.</span><span class="sxs-lookup"><span data-stu-id="ffa33-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="ffa33-105">No entanto, um ambiente do Active Directory bloqueado pode limitar as permissões exigidas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ffa33-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="ffa33-106">A preparação adequada de um ambiente do Active Directory bloqueado para o Lync Server 2013 envolve algumas considerações e etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="ffa33-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="ffa33-107">As permissões estão limitadas em um ambiente de Active Directory bloqueado de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="ffa33-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="ffa33-108">As ACEs (entradas de controle de acesso) de usuários autenticados são removidas dos contêineres.</span><span class="sxs-lookup"><span data-stu-id="ffa33-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="ffa33-109">A herança de permissões está desabilitada nos contêineres de objetos de Usuário, Contato, InetOrgPerson ou Computador.</span><span class="sxs-lookup"><span data-stu-id="ffa33-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ffa33-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ffa33-110">In This Section</span></span>

  - [<span data-ttu-id="ffa33-111">As permissões de usuário autenticado são removidas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffa33-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="ffa33-112">A herança de permissões está desabilitada em computadores, usuários ou contêiners InetOrgPerson no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffa33-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

