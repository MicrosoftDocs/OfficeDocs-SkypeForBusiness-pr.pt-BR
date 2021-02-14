---
title: Adicionar Serviços Web de Front-end 2010
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
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa dos Serviços Web do pool for , a https://pool01.contoso.net URL base será pool01.contoso.net.
ms.openlocfilehash: 96a258cd2d3c46d700dff32ea4adb6213b4de9b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824021"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="63fbf-104">Adicionar Serviços Web de Front-end 2010</span><span class="sxs-lookup"><span data-stu-id="63fbf-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="63fbf-105">A URL base é a identidade dos Serviços Web para a URL, menos o https://.</span><span class="sxs-lookup"><span data-stu-id="63fbf-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="63fbf-106">Por exemplo, se a URL completa dos Serviços Web do pool for , a https://pool01.contoso.net URL base será pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="63fbf-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="63fbf-107">Não é possível substituir o FQDN (nome de domínio totalmente qualificado) do pool de Serviços Web internos para um Servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="63fbf-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="63fbf-108">Se você estiver configurando o balanceamento de carga DNS (Sistema de Nomes de Domínio) para um pool de Front-End Enterprise Edition, poderá especificar uma URL de base interna diferente (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interna- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="63fbf-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="63fbf-109">Você pode especificar uma URL de base externa que é diferente da sua URL de base interna para diferenciar a nomenclatura de domínio.</span><span class="sxs-lookup"><span data-stu-id="63fbf-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="63fbf-110">Por exemplo, seu domínio interno é contoso.net, porém seu nome de domínio externo é contoso.com.</span><span class="sxs-lookup"><span data-stu-id="63fbf-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="63fbf-111">Você definiria a URL de base externa utilizando o nome de domínio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="63fbf-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="63fbf-112">Isto é importante para servidores de proxy reverso para uma implantação de borda.</span><span class="sxs-lookup"><span data-stu-id="63fbf-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="63fbf-113">O nome de domínio de URL de base externa deve ser o mesmo que o nome de domínio do FQDN do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="63fbf-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="63fbf-114">O sistema de mensagens instantâneas e presença exigem acesso HTTP ao pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="63fbf-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

