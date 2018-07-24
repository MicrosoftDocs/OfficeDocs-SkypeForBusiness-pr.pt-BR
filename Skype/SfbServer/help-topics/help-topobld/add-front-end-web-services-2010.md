---
title: Adicionar serviços Web de Front End 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool é https://pool01.contoso.net, a URL base é pool01. contoso.NET.
ms.openlocfilehash: 1e18c4956e9b9d369bae766ed557debe44586298
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21015701"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="2d188-104">Adicionar serviços Web de Front End 2010</span><span class="sxs-lookup"><span data-stu-id="2d188-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="2d188-105">A URL base é a identidade dos serviços Web para a URL, menos "https://".</span><span class="sxs-lookup"><span data-stu-id="2d188-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="2d188-106">Por exemplo, se a URL completa para os serviços Web do pool é https://pool01.contoso.net, a URL base é pool01. contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="2d188-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="2d188-107">Você não pode substituir o nome interno domínio totalmente qualificado de pool do Web Services (FQDN) para um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2d188-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="2d188-108">Se você estiver configurando um sistema de nome de domínio (DNS) balanceamento de carga para um pool de Front End do Enterprise Edition, você pode especificar outra URL base interna (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interna -\<sua URL base\>).</span><span class="sxs-lookup"><span data-stu-id="2d188-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="2d188-109">Você pode especificar uma URL base externa diferente-lo do seu URL base interna para diferenciar a nomeação de domínio.</span><span class="sxs-lookup"><span data-stu-id="2d188-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="2d188-110">Por exemplo, o seu domínio interno é contoso.net, mas o seu nome de domínio externo for contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2d188-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="2d188-111">Você deve definir a URL base externa usando o nome do domínio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2d188-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="2d188-112">Isso é importante para os servidores de proxy reverso para uma implantação de borda.</span><span class="sxs-lookup"><span data-stu-id="2d188-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="2d188-113">O nome de domínio de URL base externo deve ser o mesmo que o nome de domínio do FQDN do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="2d188-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="2d188-114">Mensagens instantâneas e presença requer acesso HTTP para o pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="2d188-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

