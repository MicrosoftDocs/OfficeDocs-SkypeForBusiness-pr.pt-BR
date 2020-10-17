---
title: Migrar a federação XMPP
description: Migrando a Federação XMPP.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63c9f6fd3f1c1d45de77c27417987505678f74b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543207"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="705b3-103">Migrar a federação XMPP</span><span class="sxs-lookup"><span data-stu-id="705b3-103">Migrating XMPP federation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="705b3-104">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="705b3-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="705b3-105">Versões anteriores do Lync Server e Office Communications Server forneciam um Gateway XMPP (Extensible Messaging and Presence Protocol) que pode ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP.</span><span class="sxs-lookup"><span data-stu-id="705b3-105">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="705b3-106">No Lync Server 2013, a funcionalidade do XMPP pode ser implantada como um recurso.</span><span class="sxs-lookup"><span data-stu-id="705b3-106">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="705b3-107">A funcionalidade do XMPP está instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda do Lync Server 2013 e no Gateway XMPP que é executado no servidor front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="705b3-107">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="705b3-108">De uma perspectiva de migração, uma conta de usuário do Lync Server pode ser movida para um pool do Lync Server 2013 e continuar a usar o Gateway XMPP herdado.</span><span class="sxs-lookup"><span data-stu-id="705b3-108">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="705b3-109">Isso só é possível quando o parceiro federado XMPP não está configurado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="705b3-109">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="705b3-110">Em resumo, se o Lync Server 2010 tiver sido implantado com o gateway do Office Communications Server 2007 R2 XMPP e a Federação XMPP tiver sido habilitada para usuários herdados do Lync Server 2010, para migrar a Federação do XMPP para o Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="705b3-110">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="705b3-111">Implantar um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="705b3-111">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="705b3-112">Implantar um servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="705b3-112">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="705b3-113">Mover todos os usuários para o pool do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="705b3-113">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="705b3-114">Crie políticas de acesso XMPP e certificados para o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="705b3-114">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="705b3-115">Habilite a Federação XMPP no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="705b3-115">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="705b3-116">Atualize as entradas de DNS para apontar para o gateway do Lync Server 2013 XMPP.</span><span class="sxs-lookup"><span data-stu-id="705b3-116">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

