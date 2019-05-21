---
title: Migrar a federação XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'As versões anteriores forneciam um gateway de protocolo de presença e mensagens extensível (XMPP) que poderia ser implantado como uma função de servidor separada para permitir a Federação em implantações do XMPP. A funcionalidade XMPP não está mais disponível & preterida no Skype for Business Server 2019. Se você quiser continuar com a funcionalidade do XMPP, isso pode ser avaliado em ambiente coexitence com versão herdada (Skype for Business Server 2015/Lync Server 2013). A funcionalidade XMPP é instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda herdado e o Gateway XMPP executado no servidor front-end herdado.'
ms.openlocfilehash: fd2b51af84133e28e9a4de035333b1a282d71d38
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298187"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="97bc2-106">Migrar a federação XMPP</span><span class="sxs-lookup"><span data-stu-id="97bc2-106">Migrating XMPP federation</span></span>

<span data-ttu-id="97bc2-107">As versões anteriores forneciam um gateway de protocolo de presença e mensagens extensível (XMPP) que poderia ser implantado como uma função de servidor separada para permitir a Federação em implantações do XMPP.</span><span class="sxs-lookup"><span data-stu-id="97bc2-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="97bc2-108">A funcionalidade XMPP não está mais disponível e foi preterida no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="97bc2-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="97bc2-109">Se quiser continuar com a funcionalidade do XMPP, você pode fazer isso em um ambiente de coexistência com uma versão herdada (Skype for Business Server 2015 ou Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="97bc2-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="97bc2-110">A funcionalidade XMPP é instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda herdado e o Gateway XMPP executado no servidor front-end herdado.</span><span class="sxs-lookup"><span data-stu-id="97bc2-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="97bc2-111">De uma perspectiva de migração, os usuários que desejam avaliar o recurso XMPP devem permanecer no servidor herdado e não devem ser movidos para um pool do Skype for Business Server 2019, mas continuar a usar o gateway herdado do XMPP.</span><span class="sxs-lookup"><span data-stu-id="97bc2-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="97bc2-112">Isso só é possível quando o parceiro federado do XMPP está configurado no Skype for Business Server 2015 ou no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97bc2-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="97bc2-113">Você não deve migrar o servidor de borda herdado para o Skype for Business Server 2019 se quiser continuar a funcionalidade do XMPP.</span><span class="sxs-lookup"><span data-stu-id="97bc2-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="97bc2-114">No entanto, você pode ter coexistência do servidor de borda herdado (com proxy XMPP) e do servidor de borda do Skype for Business 2019.</span><span class="sxs-lookup"><span data-stu-id="97bc2-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

