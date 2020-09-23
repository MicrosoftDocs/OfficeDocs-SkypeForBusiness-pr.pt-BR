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
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net , a URL base será pool01.contoso.net.
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219462"
---
# <a name="add-director-web-service"></a><span data-ttu-id="f09b2-104">Adicionar Serviço da Web de Diretor</span><span class="sxs-lookup"><span data-stu-id="f09b2-104">Add Director Web Service</span></span>
 
<span data-ttu-id="f09b2-105">A URL base é a identidade dos Serviços Web para a URL, menos o https://.</span><span class="sxs-lookup"><span data-stu-id="f09b2-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="f09b2-106">Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net , a URL base será pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="f09b2-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="f09b2-107">Você não pode substituir o FQDN (nome de domínio totalmente qualificado) do pool de Serviços Web internos caso esteja implantando apenas um único Diretor.</span><span class="sxs-lookup"><span data-stu-id="f09b2-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="f09b2-108">Se estiver configurando um balanceamento de carga de DNS (sistema de nomes de domínio) para o pool de diretores, você poderá especificar uma URL de base interna diferente (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interno \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="f09b2-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="f09b2-p104">Você pode especificar uma URL de base externa que é diferente da sua URL de base interna para diferenciar a nomenclatura de domínio. Por exemplo, seu domínio interno é contoso.net, porém seu nome de domínio externo é contoso.com. Você definiria a URL de base externa utilizando o nome de domínio contoso.com. Isto é importante para servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL de base externa deve ser o mesmo que o nome de domínio do FQDN do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="f09b2-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

