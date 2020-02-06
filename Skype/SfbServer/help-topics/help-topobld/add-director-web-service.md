---
title: Adicionar Serviço da Web de Diretor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.
ms.openlocfilehash: 0cdec8e371d7803bdcac781209b0fd9e55cb82be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821173"
---
# <a name="add-director-web-service"></a><span data-ttu-id="e9371-104">Adicionar Serviço da Web de Diretor</span><span class="sxs-lookup"><span data-stu-id="e9371-104">Add Director Web Service</span></span>
 
<span data-ttu-id="e9371-105">A URL base é a identidade dos serviços Web para a URL, menos "https://".</span><span class="sxs-lookup"><span data-stu-id="e9371-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="e9371-106">Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="e9371-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="e9371-107">Você não pode substituir o nome de domínio totalmente qualificado (FQDN) do pool de serviços Web interno se você estiver implantando apenas um único diretor.</span><span class="sxs-lookup"><span data-stu-id="e9371-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="e9371-108">Se você estiver configurando um balanceamento de carga de DNS (sistema de nomes de domínio) para o pool de diretores, poderá especificar uma URL base interna diferente (que deve ser diferente do FQDN do pool e pode ser\<, por exemplo\>, interna – sua URL base).</span><span class="sxs-lookup"><span data-stu-id="e9371-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="e9371-109">Você pode especificar uma URL base externa que seja diferente da URL base interna para diferenciar o nome do domínio.</span><span class="sxs-lookup"><span data-stu-id="e9371-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="e9371-110">Por exemplo, seu domínio interno é contoso.net, mas o seu nome de domínio externo é contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9371-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="e9371-111">Você definiria a URL base externa usando o nome de domínio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9371-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="e9371-112">Isso é importante para servidores proxy reverso para uma implantação de borda.</span><span class="sxs-lookup"><span data-stu-id="e9371-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="e9371-113">O nome de domínio da URL base externa deve ser igual ao nome de domínio do FQDN do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="e9371-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

