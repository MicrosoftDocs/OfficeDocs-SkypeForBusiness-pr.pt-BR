---
title: Definir FQDN de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Você cria um novo servidor de chat persistente ou pool de servidor de chat persistente usando o assistente definir novo pool de chat persistente. Selecione um pool de vários computadores ou um pool de computador único. Se você selecionar um pool de computador único e mais tarde precisar de um pool de vários computadores, será necessário remover o pool de computador único e, em seguida, definir um pool de vários computadores.
ms.openlocfilehash: 61851656b70b85db47fdad01dff0101217262dda
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217543"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="661ed-105">Definir FQDN de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="661ed-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="661ed-106">Você cria um novo servidor de chat persistente ou pool de servidor de chat persistente usando o assistente **definir novo pool de chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="661ed-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="661ed-107">Selecione um **pool de vários computadores** ou um **pool de computador único**.</span><span class="sxs-lookup"><span data-stu-id="661ed-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="661ed-108">Se você selecionar um pool de computador único e mais tarde precisar de um pool de vários computadores, será necessário remover o pool de computador único e, em seguida, definir um pool de vários computadores.</span><span class="sxs-lookup"><span data-stu-id="661ed-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="661ed-109">Você também deve definir um **FQDN de pool** para o servidor de chat persistente ou o pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="661ed-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="661ed-110">O nome de domínio totalmente qualificado (FQDN) do pool para um único pool de computador deve ser o mesmo que o FQDN do computador que compõe o pool de servidor único.</span><span class="sxs-lookup"><span data-stu-id="661ed-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="661ed-111">Para um pool de vários computadores, o FQDN deve ser o nome que você escolhe para representar esse pool de vários computadores e é definido no DNS por um registro A (e AAAA se IPv6 estiver sendo usado).</span><span class="sxs-lookup"><span data-stu-id="661ed-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="661ed-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="661ed-112">See also</span></span>

[<span data-ttu-id="661ed-113">Planejar o servidor de chat persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="661ed-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="661ed-114">Adicionar servidor de chat persistente à sua topologia do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="661ed-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
