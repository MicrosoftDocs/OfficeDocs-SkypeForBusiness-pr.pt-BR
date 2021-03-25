---
title: Adicionar Pool de Aplicativo Confiável
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir um FQDN (nome de domínio totalmente qualificado) do pool de Aplicativos Confiáveis, especifique o seguinte:'
ms.openlocfilehash: 575d4b5464b4a109bc34908f8cb86b802a20a5c0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122672"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="1c823-103">Adicionar Pool de Aplicativo Confiável</span><span class="sxs-lookup"><span data-stu-id="1c823-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="1c823-104">Para definir um FQDN (nome de domínio totalmente qualificado) do pool de Aplicativos Confiáveis, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1c823-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="1c823-105">Um FQDN do servidor ou pool de servidores que hospedará os aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="1c823-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="1c823-106">Selecione  **Pool de múltiplos computadores** caso esteja implementando um pool de servidores para os aplicativos confiáveis de balanceamento de carga e alta disponibilidade, ou selecione **Pool de computador único** caso não necessite de balanceamento de carga ou alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="1c823-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1c823-p101">Um único Servidor de Aplicativos Confiáveis não pode ser convertido para um pool de servidores posteriormente. Caso ache que precisará de um pool no futuro, agora você pode implantar um pool de múltiplos servidores contendo um único computador e adicionando servidores quando necessário.</span><span class="sxs-lookup"><span data-stu-id="1c823-p101">A single Trusted Applications Server cannot be converted to a pool of servers later. If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="1c823-109">Para maiores detalhes sobre pools de Aplicativos Confiáveis, consulte  [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1c823-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
