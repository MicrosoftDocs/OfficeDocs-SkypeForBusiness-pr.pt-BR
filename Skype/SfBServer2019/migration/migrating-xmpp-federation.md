---
title: Migrar a federação XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'As versões anteriores proporcionam um gateway XMPP (extensible messaging and presence protocol) que poderia ser implantado como uma função de servidor separada para permitir a federação com implantações XMPP. A funcionalidade XMPP não está mais disponível & foi preterida no Skype for Business Server 2019. Se você quiser continuar com a funcionalidade XMPP, isso pode ser uma ferramenta no ambiente de coexitência com a versão herdada (Skype for Business Server 2015/ Lync Server 2013). A funcionalidade XMPP é instalada em duas partes: como um proxy XMPP executado no Servidor de Borda herdado e o Gateway XMPP que é executado no Servidor Front End herdado.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752643"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="42c6f-106">Migrar a federação XMPP</span><span class="sxs-lookup"><span data-stu-id="42c6f-106">Migrating XMPP federation</span></span>

<span data-ttu-id="42c6f-107">As versões anteriores proporcionam um gateway XMPP (extensible messaging and presence protocol) que poderia ser implantado como uma função de servidor separada para permitir a federação com implantações XMPP.</span><span class="sxs-lookup"><span data-stu-id="42c6f-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="42c6f-108">A funcionalidade XMPP não está mais disponível e foi preterida no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="42c6f-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="42c6f-109">Se você quiser continuar com a funcionalidade XMPP, poderá fazer isso em um ambiente de coexistência com uma versão herdada (Skype for Business Server 2015 ou Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="42c6f-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="42c6f-110">A funcionalidade XMPP é instalada em duas partes: como um proxy XMPP executado no Servidor de Borda herdado e o Gateway XMPP que é executado no Servidor Front End herdado.</span><span class="sxs-lookup"><span data-stu-id="42c6f-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="42c6f-111">A partir de uma perspectiva de migração, os usuários que querem utilizar o recurso XMPP devem permanecer no servidor herdada e não devem ser movidos para um pool do Skype for Business Server 2019, mas continuar a usar o gateway XMPP herdada.</span><span class="sxs-lookup"><span data-stu-id="42c6f-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="42c6f-112">Isso só é possível quando o parceiro federado XMPP está configurado no Skype for Business Server 2015 ou no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42c6f-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="42c6f-113">Você não deve migrar o Servidor de Borda herdado para o Skype for Business Server 2019 se quiser continuar com a funcionalidade XMPP.</span><span class="sxs-lookup"><span data-stu-id="42c6f-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="42c6f-114">No entanto, você pode ter coexistência do Servidor de Borda herdada (com Proxy XMPP) e do Servidor de Borda do Skype for Business 2019.</span><span class="sxs-lookup"><span data-stu-id="42c6f-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

