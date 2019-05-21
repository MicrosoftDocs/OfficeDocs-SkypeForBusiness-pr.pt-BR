---
title: Adicionar Serviços Web de Front End 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.
ms.openlocfilehash: ec167b333948384a66f6ff66c64c4f53fcbe1076
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275322"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="63c42-104">Adicionar Serviços Web de Front End 2010</span><span class="sxs-lookup"><span data-stu-id="63c42-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="63c42-105">A URL base é a identidade dos serviços Web para a URL, menos "https://".</span><span class="sxs-lookup"><span data-stu-id="63c42-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="63c42-106">Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="63c42-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="63c42-107">Você não pode substituir o nome de domínio totalmente qualificado (FQDN) do pool de serviços Web interno para um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="63c42-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="63c42-108">Se você estiver configurando o balanceamento de carga do sistema de nomes de domínio (DNS) para um pool Front-end do Enterprise Edition, poderá especificar uma URL base interna diferente (que deve ser diferente do FQDN do pool e\<poderia ser,\>por exemplo, interna – sua URL base).</span><span class="sxs-lookup"><span data-stu-id="63c42-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="63c42-109">Você pode especificar uma URL base externa que seja diferente da URL base interna para diferenciar o nome do domínio.</span><span class="sxs-lookup"><span data-stu-id="63c42-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="63c42-110">Por exemplo, seu domínio interno é contoso.net, mas o seu nome de domínio externo é contoso.com.</span><span class="sxs-lookup"><span data-stu-id="63c42-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="63c42-111">Você definiria a URL base externa usando o nome de domínio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="63c42-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="63c42-112">Isso é importante para servidores proxy reverso para uma implantação de borda.</span><span class="sxs-lookup"><span data-stu-id="63c42-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="63c42-113">O nome de domínio da URL base externa deve ser igual ao nome de domínio do FQDN do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="63c42-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="63c42-114">Mensagens instantâneas e presença exigem acesso HTTP ao pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="63c42-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

