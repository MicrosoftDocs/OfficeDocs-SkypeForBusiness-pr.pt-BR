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
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Você cria um novo servidor de chat persistente ou um pool de servidores de chat persistentes usando o assistente para definir novo pool de chat persistente. Selecione um  Pool de vários computadores ou um Pool com um único computador. Se você selecionar um pool com um único computador e precisar mais tarde de um pool com vários computadores, será necessário remover o pool com um único computador e definir um pool com vários computadores.
ms.openlocfilehash: 0a30073d4b4df28eadaa206778adeb59651b1a48
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684824"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="aad42-105">Definir FQDN de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="aad42-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="aad42-106">Você cria um novo servidor de chat persistente ou um pool de servidores de chat persistentes usando o assistente para **definir novo pool de chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="aad42-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="aad42-107">Selecione um  **Pool de vários computadores** ou um **Pool com um único computador**.</span><span class="sxs-lookup"><span data-stu-id="aad42-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="aad42-108">Se você selecionar um pool com um único computador e precisar mais tarde de um pool com vários computadores, será necessário remover o pool com um único computador e definir um pool com vários computadores.</span><span class="sxs-lookup"><span data-stu-id="aad42-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="aad42-109">Você também deve definir um **FQDN de pool** para o servidor de chat persistente ou o pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="aad42-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="aad42-110">O nome de domínio totalmente qualificado (FQDN) de um pool com um único computador precisa ser o mesmo que o FQDN do computador que compõe o pool com um único computador.</span><span class="sxs-lookup"><span data-stu-id="aad42-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="aad42-111">Para um pool com vários computadores, o FQDN precisa ser o nome que você escolher para representar esse pool e precisa ser definido em DNS por um registro de host A (e AAAA se IPv6 estiver sendo usado).</span><span class="sxs-lookup"><span data-stu-id="aad42-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aad42-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="aad42-112">See also</span></span>

[<span data-ttu-id="aad42-113">Planejar Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="aad42-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="aad42-114">Adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="aad42-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
