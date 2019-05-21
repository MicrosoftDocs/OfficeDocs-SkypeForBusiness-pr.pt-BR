---
title: Adicionar Pool de Aplicativo Confiável
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Para definir um FQDN (nome de domínio totalmente qualificado) do pool de aplicativos confiáveis, especifique o seguinte:'
ms.openlocfilehash: 27957348d4c6dc6b277a37d458ff21bb5efabc17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303621"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="19c85-103">Adicionar Pool de Aplicativo Confiável</span><span class="sxs-lookup"><span data-stu-id="19c85-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="19c85-104">Para definir um FQDN (nome de domínio totalmente qualificado) do pool de aplicativos confiáveis, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="19c85-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="19c85-105">Um FQDN do servidor ou pool de servidores que hospedará os aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="19c85-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="19c85-106">Selecione **vários pools de computadores** se você estiver implantando um pool de servidores para os aplicativos confiáveis de balanceamento de carga e alta disponibilidade, ou selecione **um pool de computador único** se você não precisar de balanceamento de carga ou de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="19c85-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="19c85-107">Um único servidor de aplicativos confiáveis não pode ser convertido em um pool de servidores mais tarde.</span><span class="sxs-lookup"><span data-stu-id="19c85-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="19c85-108">Se você acha que pode precisar de um pool no futuro, poderá implantar um pool de vários servidores com um único computador agora e adicionar servidores quando necessário.</span><span class="sxs-lookup"><span data-stu-id="19c85-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="19c85-109">Para obter detalhes sobre pools de aplicativos confiáveis, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="19c85-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

