---
title: Adicionar Serviços Web de Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net , a URL base será pool01.contoso.net.
ms.openlocfilehash: 45705ea940fa0f43f600546a680d76b41b645e59
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217932"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="6cee7-104">Adicionar Serviços Web de Front End</span><span class="sxs-lookup"><span data-stu-id="6cee7-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="6cee7-105">A URL base é a identidade dos Serviços Web para a URL, menos o https://.</span><span class="sxs-lookup"><span data-stu-id="6cee7-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="6cee7-106">Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net , a URL base será pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="6cee7-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="6cee7-107">Você não pode substituir o FQDN (nome de domínio totalmente qualificado) do pool de Serviços Web internos por um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6cee7-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="6cee7-108">Se estiver configurando o balanceamento de carga do DNS (sistema de nomes de domínio) para um pool de front-ends Enterprise Edition, você poderá especificar uma URL base interna diferente, que deve ser diferente do FQDN do pool (por exemplo, Internal- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="6cee7-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="6cee7-p104">É possível especificar uma URL de base externa diferente de sua URL de base interna para diferenciar a designação de domínios. Por exemplo, seu domínio interno é contoso.net, mas seu nome de domínio externo é contoso.com; você definiria a URL de base externa usando o nome de domínio contoso.com. Isso é importante para servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL de base externa deve ser o mesmo que o nome de domínio do FQDN do proxy reverso. Mensagens instantâneas e presença exigem acesso HTTP ao pool de Front-Ends.</span><span class="sxs-lookup"><span data-stu-id="6cee7-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy. Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

