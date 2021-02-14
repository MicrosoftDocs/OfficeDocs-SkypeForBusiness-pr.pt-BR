---
title: Adicionar Serviços Web de Front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa dos Serviços Web do pool for , a https://pool01.contoso.net URL base será pool01.contoso.net.
ms.openlocfilehash: 171cc8c912e1a1204d07be2c52c0e96bc1369991
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823981"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="652fe-104">Adicionar Serviços Web de Front-end</span><span class="sxs-lookup"><span data-stu-id="652fe-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="652fe-105">A URL base é a identidade dos Serviços Web para a URL, menos o https://.</span><span class="sxs-lookup"><span data-stu-id="652fe-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="652fe-106">Por exemplo, se a URL completa dos Serviços Web do pool for , a https://pool01.contoso.net URL base será pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="652fe-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="652fe-107">Você não pode substituir o FQDN (nome de domínio totalmente qualificado) do pool de Serviços Web internos por um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="652fe-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="652fe-108">Se você estiver configurando o balanceamento de carga DNS (Sistema de Nomes de Domínio) para um pool de Front-End Enterprise Edition, poderá especificar uma URL de base interna diferente, que deve ser diferente do FQDN do pool (por exemplo, interno- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="652fe-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="652fe-p104">É possível especificar uma URL de base externa diferente de sua URL de base interna para diferenciar a designação de domínios. Por exemplo, seu domínio interno é contoso.net, mas seu nome de domínio externo é contoso.com; você definiria a URL de base externa usando o nome de domínio contoso.com. Isso é importante para servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL de base externa deve ser o mesmo que o nome de domínio do FQDN do proxy reverso. Mensagens instantâneas e presença exigem acesso HTTP ao pool de Front-Ends.</span><span class="sxs-lookup"><span data-stu-id="652fe-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy. Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

