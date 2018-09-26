---
title: Migração da federação XMPP
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Versões anteriores forneciam um gateway de protocolo XMPP extensível para mensagens e presença que poderia ser implantado como uma função de servidor separadas para permitir a federação com implantações de XMPP. A funcionalidade XMPP não está mais disponível & preteridos no Skype para Business Server 2019. Se você deseja continuar com a funcionalidade XMPP, que pode ser avaliado no ambiente coexitence com a versão herdada (Skype para Business Server 2015 / Lync Server 2013). Funcionalidade XMPP está instalada em duas partes: como um XMPP proxy que é executado no antigo servidor de borda e o Gateway XMPP que é executado no servidor Front-End herdado.'
ms.openlocfilehash: d8db32bd823e4a0c15fa373f89ee930d2cd8d98c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029864"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="9a8af-106">Migração da federação XMPP</span><span class="sxs-lookup"><span data-stu-id="9a8af-106">Migrating XMPP federation</span></span>

<span data-ttu-id="9a8af-107">Versões anteriores forneciam um gateway de protocolo XMPP extensível para mensagens e presença que poderia ser implantado como uma função de servidor separadas para permitir a federação com implantações de XMPP.</span><span class="sxs-lookup"><span data-stu-id="9a8af-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="9a8af-108">A funcionalidade XMPP não está mais disponível e foi preterida no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9a8af-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="9a8af-109">Se você deseja continuar com a funcionalidade XMPP, você pode fazer isso em um ambiente de coexistência com uma versão herdada (Skype para Business Server 2015 ou o Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="9a8af-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="9a8af-110">Funcionalidade XMPP está instalada em duas partes: como um XMPP proxy que é executado no antigo servidor de borda e o Gateway XMPP que é executado no servidor Front-End herdado.</span><span class="sxs-lookup"><span data-stu-id="9a8af-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="9a8af-111">De uma perspectiva de migração, os usuários que desejam avaliar o recurso XMPP devem permanecer em servidor herdado e não devem ser movidos para um Skype para Business Server 2019 pool, mas continuam a usar o gateway XMPP herdado.</span><span class="sxs-lookup"><span data-stu-id="9a8af-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="9a8af-112">Isso é possível somente quando o parceiro federado XMPP está configurado no Skype para Business Server 2015 ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a8af-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="9a8af-113">Você não deve migrar o servidor de borda herdado para Skype para Business Server 2019 se você deseja continuar com a funcionalidade XMPP.</span><span class="sxs-lookup"><span data-stu-id="9a8af-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="9a8af-114">No entanto, você pode ter coexistência do servidor de borda herdado (com o Proxy XMPP) e o Skype para servidor de borda de 2019 de negócios.</span><span class="sxs-lookup"><span data-stu-id="9a8af-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

