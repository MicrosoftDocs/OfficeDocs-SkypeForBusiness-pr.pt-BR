---
title: Definir FQDN de Chat Persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Você cria um novo servidor de Chat persistente ou o pool de servidor de Chat persistente usando o assistente Definir Novo Pool de Chat persistente. Selecione um pool de computador único ou um pool de vários computadores. Se você selecionar um pool com um único computador e precisar mais tarde de um pool com vários computadores, será necessário remover o pool com um único computador e definir um pool com vários computadores.
ms.openlocfilehash: 419eab5bb6f92c3b0859214042e59378b5d8c601
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2018
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="935f6-105">Definir FQDN de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="935f6-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="935f6-106">Você cria um novo servidor de Chat persistente ou o pool de servidor de Chat persistente usando o assistente **Definir Novo Pool de Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="935f6-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="935f6-107">Selecione um  **Pool de vários computadores** ou um **Pool com um único computador**.</span><span class="sxs-lookup"><span data-stu-id="935f6-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="935f6-108">Se você selecionar um pool com um único computador e precisar mais tarde de um pool com vários computadores, será necessário remover o pool com um único computador e definir um pool com vários computadores.</span><span class="sxs-lookup"><span data-stu-id="935f6-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="935f6-109">Você também deve definir um **FQDN do Pool** para o servidor de Chat persistente ou o pool de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="935f6-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="935f6-110">O nome de domínio totalmente qualificado (FQDN) de um pool com um único computador precisa ser o mesmo que o FQDN do computador que compõe o pool com um único computador.</span><span class="sxs-lookup"><span data-stu-id="935f6-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="935f6-111">Para um pool com vários computadores, o FQDN precisa ser o nome que você escolher para representar esse pool e precisa ser definido em DNS por um registro de host A (e AAAA se IPv6 estiver sendo usado).</span><span class="sxs-lookup"><span data-stu-id="935f6-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="935f6-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="935f6-112">See also</span></span>

#### 

[<span data-ttu-id="935f6-113">Planejar o servidor de Chat persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="935f6-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="935f6-114">Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015</span><span class="sxs-lookup"><span data-stu-id="935f6-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

