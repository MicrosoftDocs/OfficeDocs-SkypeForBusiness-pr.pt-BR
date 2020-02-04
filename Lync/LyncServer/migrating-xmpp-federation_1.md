---
title: Migrar a federação XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 953b422527e095a6fef1e34cbf8b8fde2d494f42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="57168-102">Migrar a federação XMPP</span><span class="sxs-lookup"><span data-stu-id="57168-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57168-103">_**Tópico da última modificação:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="57168-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="57168-104">As versões anteriores do Office Communications Server forneciam um gateway Extensible Messaging and Presence Protocol (XMPP) que poderia ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP.</span><span class="sxs-lookup"><span data-stu-id="57168-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="57168-105">No Lync Server 2013, a funcionalidade XMPP pode ser implantada como um recurso.</span><span class="sxs-lookup"><span data-stu-id="57168-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="57168-106">A funcionalidade XMPP é instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda do Lync Server 2013 e o Gateway XMPP executado no servidor front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57168-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="57168-107">De uma perspectiva de migração, uma conta de usuário do Office Communications Server 2007 R2 pode ser movida para um pool do Lync Server 2013 e continuar a usar o gateway do Office Communications Server 2007 R2 XMPP.</span><span class="sxs-lookup"><span data-stu-id="57168-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="57168-108">Isso só é possível quando o parceiro federado XMPP não está configurado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57168-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="57168-109">Em resumo, se o Office Communications Server tiver sido implantado com o gateway do Office Communications Server 2007 R2 e a Federação do XMPP tiver sido habilitada para usuários herdados do Office Communications Server 2007 R2, para migrar a Federação do XMPP para o Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="57168-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="57168-110">Implantar um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57168-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="57168-111">Implantar um servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57168-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="57168-112">Mover todos os usuários para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57168-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="57168-113">Criar políticas e certificados de acesso XMPP para o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="57168-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="57168-114">Habilite a Federação do XMPP no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57168-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="57168-115">Atualize as entradas de DNS para apontar para o gateway do Lync Server 2013 XMPP.</span><span class="sxs-lookup"><span data-stu-id="57168-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

