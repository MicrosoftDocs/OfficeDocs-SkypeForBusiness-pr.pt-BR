---
title: Cenário de migração padrão-alto nível
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0acdf50ac515810b2813a98e9dc1f289e327eba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="8615c-102">Cenário de migração padrão-alto nível</span><span class="sxs-lookup"><span data-stu-id="8615c-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8615c-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="8615c-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="8615c-104">Use os itens a seguir como ponto de partida ao migrar o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat para o Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8615c-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="8615c-105">O caminho de migração padrão do Lync Server 2013 é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8615c-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="8615c-106">Sua organização implantou anteriormente o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat e você deseja implantar o Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8615c-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="8615c-107">Implantar o Lync Server 2013 e implantar pool (s) do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8615c-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="8615c-108">Preparar e planejar a migração de salas de chat persistentes e determinar um tempo apropriado para desligar o sistema para migração.</span><span class="sxs-lookup"><span data-stu-id="8615c-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="8615c-109">Execute os cmdlets do Windows PowerShell para migração (**Export-CsPersistentChatData** e **Import-CsPersistentChatData**) para mover o conteúdo para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8615c-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="8615c-110">Verifique se a migração foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="8615c-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="8615c-111">Encerre sua implantação herdada.</span><span class="sxs-lookup"><span data-stu-id="8615c-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="8615c-112">Configure o servidor de chat persistente para que os clientes herdados possam se conectar ao Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8615c-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="8615c-113">Isso é necessário pois demora um tempo para implantar novos clientes, e você deseja permitir que os usuários existentes com clientes herdados tenham acesso às suas salas de chat o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="8615c-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="8615c-114">Implantar novos clientes, enquanto continua a ajudar a garantir que os funcionários com o chat de grupo herdado (clientes) possam acessar suas salas de chat.</span><span class="sxs-lookup"><span data-stu-id="8615c-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

