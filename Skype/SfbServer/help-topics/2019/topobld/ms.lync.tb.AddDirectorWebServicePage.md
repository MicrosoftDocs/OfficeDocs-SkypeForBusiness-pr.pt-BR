---
title: Adicionar serviço da Web de diretor
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool é https://pool01.contoso.net, a URL base é pool01. contoso.NET.
ms.openlocfilehash: 2350a728580d89e5ff1e18106c558ec817ab2f37
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21061803"
---
# <a name="add-director-web-service"></a><span data-ttu-id="2d387-104">Adicionar serviço da Web de diretor</span><span class="sxs-lookup"><span data-stu-id="2d387-104">Add Director Web Service</span></span>
 
<span data-ttu-id="2d387-105">A URL base é a identidade dos serviços Web para a URL, menos "https://".</span><span class="sxs-lookup"><span data-stu-id="2d387-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="2d387-106">Por exemplo, se a URL completa para os serviços Web do pool é https://pool01.contoso.net, a URL base é pool01. contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="2d387-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="2d387-107">Se você estiver implantando somente um único diretor, você não pode substituir o nome de domínio totalmente qualificado da pool do Web Services interno (FQDN).</span><span class="sxs-lookup"><span data-stu-id="2d387-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="2d387-108">Se você estiver configurando uma sistema de nome de domínio (DNS) balanceamento de carga do pool de diretores, você poderá especificar outra URL base interna (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interna -\<sua URL base\>).</span><span class="sxs-lookup"><span data-stu-id="2d387-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="2d387-109">Você pode especificar uma URL base externa diferente-lo do seu URL base interna para diferenciar a nomeação de domínio.</span><span class="sxs-lookup"><span data-stu-id="2d387-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="2d387-110">Por exemplo, o seu domínio interno é contoso.net, mas o seu nome de domínio externo for contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2d387-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="2d387-111">Você deve definir a URL base externa usando o nome do domínio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2d387-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="2d387-112">Isso é importante para os servidores de proxy reverso para uma implantação de borda.</span><span class="sxs-lookup"><span data-stu-id="2d387-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="2d387-113">O nome de domínio de URL base externo deve ser o mesmo que o nome de domínio do FQDN do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="2d387-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

